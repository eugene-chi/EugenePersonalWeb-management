<style lang="less">
    @import '../../styles/common.less';
    @import 'less/page1.1.less';
</style>

<template>
    <div class="jinjian-page">

        <Card>
            <Table :loading="loading" :columns="columns1" :data="table1"></Table>
            <div style="margin: 10px;overflow: hidden">
                <div style="float: right;">
                    <Page :current="page" :total="totalRecord" :page-size="size" @on-change="changePage"></Page>
                </div>
            </div>
        </Card>

    </div>
</template>
<script>
    export default {
        data () {
            return {
                page: 1,
                size: 10,
                totalRecord: 0,
                loading: true,
                columns1: [
                    {
                        key: 'id',
                        title: '商户设备id'
                    },
                    {
                        key: 'merchantId',
                        title: '商户设备id'
                    },
                    {
                        key: 'terminalNo',
                        title: '终端编号'
                    },
                    {
                        key: 'terminalType',
                        title: '终端类型'
                    },
                    {
                        key: 'status',
                        title: '状态'
                    },
                    {
                        key: 'cdatetime',
                        title: '创建时间'
                    },
                ],//表头
                table1: [],
            };
        },
        mounted(){
            this.showTable();
        },
        methods: {
            showTable(){//加载表格

                this.loading = true; // 加载遮罩打开
                this.$http.get(
                    '/terminals',
                    {
                        params: {
                            page: this.page,
                            size: this.size,
                        }
                    })
                    .then(res => {
                        console.info(res.data);
                        if (0 != res.data.status) {
                            // 显示加载数据出现错误
                            this.$Message.error(res.data.errMsg)
                        } else {
                            //成功
                            this.table1 = []; // 清空表格
                            this.totalRecord = res.data.payload.totalRecord;//总条数，分页用
                            if (res.data.payload.totalRecord > 0) {
                                res.data.payload.items.forEach((item, i) => {
                                    this.table1.push(item);
                                })
                            }
                            this.loading = false; // 加载遮罩关闭
                        }
                    }).catch(error => {
                    if ('undefined' == typeof(error.response)) {
                        this.$Message.error(error.message)
                    } else {
                        this.$Message.error(error.response.data.errMsg)
                    }
                })
            },
            changePage (page) {
                this.page = page;
                this.showTable();
            }
        }
    };
</script>
