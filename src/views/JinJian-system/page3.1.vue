<style lang="less">
    @import '../../styles/common.less';
    @import 'less/page1.1.less';
</style>

<template>
    <div class="jinjian-page">
        <Form ref="formValidate" :model="formValidate" :rules="ruleValidate" label-position="top">

        <Card>
            <p slot="title">
                商户终端信息录入
            </p>
            <Row class="my-row" :gutter="16" type="flex" align="middle">
                <Col span="12">
                <FormItem label="选择机构医院" prop="merchGroupId">
                <Select v-model="formValidate.merchantId">
                    <Option v-for="item in merchantList" :value="item.id" :key="item.id">
                        {{ item.fullName }}
                    </Option>
                </Select>
                </FormItem>
                </Col>
            </Row>
            <Row class="my-row" :gutter="16" type="flex" align="middle">
                <Col span="12">
                <FormItem label="终端编号" prop="terminalNo">

                <Input v-model="formValidate.terminalNo"></Input>
                </FormItem>
                </Col>
                <Col span="6">
                    <FormItem label="设备类型" prop="merchGroupId">
                <Select v-model="formValidate.terminalType">
                    <Option v-for="item in terminalTypeList" :value="item.type" :key="item.type">
                        {{ item.name }}
                    </Option>
                </Select>
                    </FormItem>
                </Col>

                <!--<Col span="6">-->
                <!--<Input v-model="terminalType"></Input>-->
                <!--</Col>-->
            </Row>

        </Card>
        </Form>

        <Button class="margin-top-10" type="primary" @click="submit('formValidate')">保存</Button>
    </div>
</template>

<script>
    import qs from 'qs';
    import data from './data/terminalTypeList.json'

    export default {
        data () {
            return {
                merchantList: [],
                terminalTypeList: [],
                formValidate:{
                    merchantId: '',
                    terminalType: '',
                    terminalNo: '',

                },
                ruleValidate: {
                    merchantId: [
                        {required: true, message: '不能为空', trigger: 'change'}
                    ],
                    terminalType: [
                        {required: true, message: '不能为空', trigger: 'change'}
                    ],
                    terminalNo: [
                        {required: true, message: '不能为空', trigger: 'blur'}
                    ]
                }


            };
        },
        methods: {
            //获取机构医院列表
            getMerchants(){
                this.$http.get(
                    '/merchants',
                    {
                        params: {
                            page: 1,
                            size: 10000,
                        }
                    })
                    .then(res => {
                        console.info(res.data);
                        if (0 != res.data.status) {
                            // 显示加载数据出现错误
                            this.$Message.error(res.data.errMsg)
                        } else {
                            //成功
                            this.merchantList = []; // 清空列表
                            if (res.data.payload.totalRecord > 0) {
                                res.data.payload.items.forEach((item, i) => {
                                    this.merchantList.push(item);
                                });
                            }
                        }
                    }).catch(error => {
                    if ('undefined' == typeof(error.response)) {
                        this.$Message.error(error.message)
                    } else {
                        this.$Message.error(error.response.data.errMsg)
                    }
                })
            },
            //保存信息
            submit(name){
                this.$refs[name].validate((valid) => {
                        if (valid) {
                            this.$Message.success('Success!');

                this.$http.post(
                    '/terminal',
                    qs.stringify({
                        merchantId: this.formValidate.merchantId,
                        terminalNo: this.formValidate.terminalNo,
                        terminalType: this.formValidate.terminalType,
                    })
                ).then((res) => {
                    console.log(res.data.status + ':' + res.data.errMsg);
                    if (0 != res.data.status) {
                        this.$Message.error('信息填写有误');
                    } else {
                        // 成功
                        this.$Message.success('提交成功');
                        this.handleReset('formValidate');
                    }
                }).catch(error => {
                    // 响应错误回调
                    if ('undefined' == typeof(error.response)) {
                        this.$Message.error(error.message)
                    } else {
                        this.$Message.error(error.response.data.errMsg)
                    }
                });

                        } else {
                            this.$Message.error('信息填写有误!');
                        }
                });
            },
            //清空填写
            handleReset (name) {
                this.$refs[name].resetFields();
            }

        },
        mounted () {
            this.terminalTypeList = data;
            this.getMerchants();
        }
    };
</script>
