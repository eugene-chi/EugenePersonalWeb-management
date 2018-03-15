<style lang="less">
    @import '../../styles/common.less';
    @import 'less/page1.1.less';
</style>

<template>
    <div class="jinjian-page">
        <Form ref="formValidate" :model="formValidate" :rules="ruleValidate" label-position="top">

            <Card>
                <p slot="title">
                    支付渠道信息录入
                </p>
                <Row class="my-row" :gutter="16" type="flex" align="middle">
                    <Col span="12">
                    <FormItem label="支付渠道简称" prop="name">
                        <Input v-model="formValidate.name"></Input>
                    </FormItem>
                    </Col>
                    <Col span="12">
                    <FormItem label="支付渠道全名" prop="fullName">
                        <Input v-model="formValidate.fullName"></Input>
                    </FormItem>
                    </Col>
                </Row>
                <Row class="my-row" :gutter="16" type="flex" align="middle">
                    <Col span="12">
                    <FormItem label="该支付渠道下 为我们公司分配的Id" prop="associateId">
                        <Input v-model="formValidate.associateId"></Input>
                    </FormItem>
                    </Col>
                </Row>

            </Card>
        </Form>

        <Button class="margin-top-10" type="primary" @click="submit('formValidate')">保存</Button>
    </div>
</template>

<script>
    import qs from 'qs';

    export default {
        data () {
            return {
                formValidate: {
                    name: '',
                    fullName: '',
                    associateId: '',
                },
                ruleValidate: {
                    name: [
                        {required: true, message: '不能为空', trigger: 'blur'}
                    ],
                    fullName: [
                        {required: true, message: '不能为空', trigger: 'blur'}
                    ],
                    associateId: [
                        {required: true, message: '不能为空', trigger: 'blur'}
                    ]
                }

            };
        },
        methods: {
            //保存信息
            submit(name){
                this.$refs[name].validate((valid) => {
                    if (valid) {
                        this.$Message.success('Success!');

                        this.$http.post(
                            '/paychannel',
                            qs.stringify({
                                name: this.formValidate.name,
                                fullName: this.formValidate.fullName,
                                associateId: this.formValidate.associateId,
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
    };
</script>
