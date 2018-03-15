<style lang="less">
    @import '../../styles/common.less';
    @import 'less/page1.1.less';
</style>

<template>
    <div class="jinjian-page">
        <Form ref="formValidate" :model="formValidate" :rules="ruleValidate" label-position="top">
            <Card>
                <p slot="title">
                    医院基本信息录入
                </p>

                <Row class="my-row" :gutter="16" type="flex" align="middle">
                    <Col span="12">
                    <FormItem label="集团公司简称" prop="name">
                        <Input v-model="formValidate.name"></Input>
                    </FormItem>
                    </Col>
                    <Col span="12">
                    <FormItem label="集团公司全称" prop="fullName">
                        <Input v-model="formValidate.fullName"></Input>
                    </FormItem>
                    </Col>
                </Row>
                <Row class="my-row" :gutter="16" type="flex" align="middle">
                    <Col span="24">
                    <FormItem label="注册地址" prop="registerAddress">
                        <Input v-model="formValidate.registerAddress"></Input>
                    </FormItem>
                    </Col>
                </Row>
                <Row class="my-row" :gutter="16" type="flex" align="middle">
                    <Col span="24">
                    <FormItem label="经营地址" prop="operateAddress">
                        <Input v-model="formValidate.operateAddress"></Input>
                    </FormItem>
                    </Col>
                </Row>
                <Row class="my-row" :gutter="16" type="flex" align="middle">
                    <Col span="12">
                    <FormItem label="营业执照编号" prop="bizLicenseNo">
                        <Input v-model="formValidate.bizLicenseNo"></Input>
                    </FormItem>
                    </Col>

                    <Col span="6">
                    <FormItem label="证件开始日期" prop="bizLicenseBeginDate">
                        <DatePicker v-model="formValidate.bizLicenseBeginDate" type="date" placeholder="Select date"
                                    style="width: 120px"></DatePicker>
                    </FormItem>
                    </Col>
                    <Col span="6">
                    <FormItem label="证件结束日期" prop="bizLicenseFinalDate">

                        <DatePicker v-model="formValidate.bizLicenseFinalDate" type="date" placeholder="Select date"
                                    style="width: 120px"></DatePicker>

                    </FormItem>
                    </Col>

                </Row>
                <Row class="my-row" :gutter="16" type="flex" align="middle">
                    <Col span="12">
                    <FormItem label="上传营业执照扫描件">

                        <Upload action="//jsonplaceholder.typicode.com/posts/">
                            <Button type="ghost" icon="ios-cloud-upload-outline">上传文件</Button>
                        </Upload>
                    </FormItem>
                    </Col>
                </Row>
                <Row class="my-row" :gutter="16" type="flex" align="middle">
                    <Col span="12">
                    <FormItem label="税务登记证编号" prop="taxEnrolCertificateNo">

                        <Input v-model="formValidate.taxEnrolCertificateNo"></Input>
                    </FormItem>
                    </Col>
                    <Col span="6">
                    <FormItem label="证件签发日期" prop="taxEnrolCertificateIssueDate">

                        <DatePicker v-model="formValidate.taxEnrolCertificateIssueDate" type="date"
                                    placeholder="Select date"
                                    style="width: 120px"></DatePicker>
                    </FormItem>
                    </Col>
                </Row>
                <Row class="my-row" :gutter="16" type="flex" align="middle">
                    <Col span="6">
                    <FormItem label="上传税务登记证扫描件">

                        <Upload action="//jsonplaceholder.typicode.com/posts/">
                            <Button type="ghost" icon="ios-cloud-upload-outline">上传文件</Button>
                        </Upload>
                    </FormItem>
                    </Col>
                </Row>
                <Row class="my-row" :gutter="16" type="flex" align="middle">
                    <Col span="12">
                    <FormItem label="组织机构代码证 代码" prop="organizationCodeCertificateNo">
                        <Input v-model="formValidate.organizationCodeCertificateNo"></Input>
                    </FormItem>
                    </Col>
                    <Col span="6">
                    <FormItem label="证件开始日期" prop="organizationCodeCertificateBeginDate">

                        <DatePicker v-model="formValidate.organizationCodeCertificateBeginDate" type="date"
                                    placeholder="Select date"
                                    style="width: 120px"></DatePicker>
                    </FormItem>
                    </Col>
                    <Col span="6">
                    <FormItem label="证件结束日期" prop="organizationCodeCertificateFinalDate">

                        <DatePicker v-model="formValidate.organizationCodeCertificateFinalDate" type="date"
                                    placeholder="Select date"
                                    style="width: 120px"></DatePicker>
                    </FormItem>
                    </Col>
                </Row>
                <Row class="my-row" :gutter="16" type="flex" align="middle">
                    <Col span="6">
                    <FormItem label="上传组织机构代码证扫描件">

                        <Upload action="//jsonplaceholder.typicode.com/posts/">
                            <Button type="ghost" icon="ios-cloud-upload-outline">上传文件</Button>
                        </Upload>
                    </FormItem>
                    </Col>
                </Row>
                <Row class="my-row" :gutter="16" type="flex" align="middle">
                    <Col span="12">
                    <FormItem label="企业法人姓名" prop="legalPerson">
                        <Input v-model="formValidate.legalPerson"></Input>
                    </FormItem>
                    </Col>
                    <Col span="12">
                    <FormItem label="企业法人身份证号码" prop="legalPersonIdCardNo">

                        <Input v-model="formValidate.legalPersonIdCardNo"></Input>
                    </FormItem>
                    </Col>
                </Row>
                <Row class="my-row" :gutter="16" type="flex" align="middle">
                    <Col span="6">
                    <FormItem label="证件开始日期" prop="legalPersonIdCardBeginDate">

                        <DatePicker v-model="formValidate.legalPersonIdCardBeginDate" type="date"
                                    placeholder="Select date"
                                    style="width: 120px"></DatePicker>
                    </FormItem>
                    </Col>
                    <Col span="6">
                    <FormItem label="证件结束日期" prop="legalPersonIdCardFinalDate">

                        <DatePicker v-model="formValidate.legalPersonIdCardFinalDate" type="date"
                                    placeholder="Select date"
                                    style="width: 120px"></DatePicker>
                    </FormItem>
                    </Col>
                </Row>
                <Row class="my-row" :gutter="16" type="flex" align="middle">
                    <Col span="12">
                    <FormItem label="控股股东及实际控股人" prop="shareholder">

                        <Input v-model="formValidate.shareholder"></Input>
                    </FormItem>
                    </Col>
                </Row>

            </Card>
            <Card class="margin-top-10">
                <p slot="title">
                    合办人信息
                </p>
                <Row class="my-row" :gutter="16" type="flex" align="middle">
                    <Col span="6">
                    <FormItem label="授权办理业务人员姓名" prop="accreditBizPerson">

                        <Input v-model="formValidate.accreditBizPerson"></Input>
                    </FormItem>
                    </Col>
                    <Col span="12">
                    <FormItem label="授权办理业务人员身份证号" prop="accreditBizPersonIdCardNo">

                        <Input v-model="formValidate.accreditBizPersonIdCardNo"></Input>
                    </FormItem>
                    </Col>
                </Row>
                <Row class="my-row" :gutter="16" type="flex" align="middle">
                    <Col span="6">
                    <FormItem label="证件开始日期" prop="accreditBizPersonIdCardBeginDate">

                        <DatePicker v-model="formValidate.accreditBizPersonIdCardBeginDate" type="date"
                                    placeholder="Select date"
                                    style="width: 120px"></DatePicker>
                    </FormItem>
                    </Col>
                    <Col span="6">
                    <FormItem label="证件结束日期" prop="accreditBizPersonIdCardFinalDate">

                        <DatePicker v-model="formValidate.accreditBizPersonIdCardFinalDate" type="date"
                                    placeholder="Select date"
                                    style="width: 120px"></DatePicker>
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
    //时间格式转化
    import moment from 'moment';

    export default {
        data () {
            return {
                formValidate: {
                    name: '',
                    fullName: '',
                    registerAddress: '',
                    operateAddress: '',
                    bizLicenseNo: '',
                    bizLicenseBeginDate: '',
                    bizLicenseFinalDate: '',
                    bizLicenseFileUrl: '',
                    taxEnrolCertificateNo: '',
                    taxEnrolCertificateIssueDate: '',
                    taxEnrolCertificateFileUrl: '',
                    organizationCodeCertificateNo: '',
                    organizationCodeCertificateBeginDate: '',
                    organizationCodeCertificateFinalDate: '',
                    organizationCodeCertificateFileUrl: '',
                    legalPerson: '',
                    legalPersonIdCardNo: '',
                    legalPersonIdCardBeginDate: '',
                    legalPersonIdCardFinalDate: '',
                    shareholder: '',
                    accreditBizPerson: '',
                    accreditBizPersonIdCardNo: '',
                    accreditBizPersonIdCardBeginDate: '',
                    accreditBizPersonIdCardFinalDate: '',
                    status: '',
                    provinceNo: '',
                },
                ruleValidate: {
                    name: [
                        {required: true, message: '不能为空', trigger: 'blur'}
                    ],
                    fullName: [
                        {required: true, message: '不能为空', trigger: 'blur'}
                    ],
                    registerAddress: [
                        {required: true, message: '不能为空', trigger: 'blur'}
                    ],
                    operateAddress: [
                        {required: true, message: '不能为空', trigger: 'blur'}
                    ],
                    bizLicenseNo: [
                        {required: true, message: '不能为空', trigger: 'blur'}
                    ],
                    bizLicenseBeginDate: [
                        {required: true, message: '不能为空', trigger: 'change', type: 'date'}
                    ],
                    bizLicenseFinalDate: [
                        {required: true, message: '不能为空', trigger: 'change', type: 'date'}
                    ],
                    taxEnrolCertificateNo: [
                        {required: true, message: '不能为空', trigger: 'blur'}
                    ],
                    taxEnrolCertificateIssueDate: [
                        {required: true, message: '不能为空', trigger: 'change', type: 'date'}
                    ],
                    organizationCodeCertificateNo: [
                        {required: true, message: '不能为空', trigger: 'blur'}
                    ],
                    organizationCodeCertificateBeginDate: [
                        {required: true, message: '不能为空', trigger: 'change', type: 'date'}
                    ],
                    organizationCodeCertificateFinalDate: [
                        {required: true, message: '不能为空', trigger: 'change', type: 'date'}
                    ],
                    legalPerson: [
                        {required: true, message: '不能为空', trigger: 'blur'}
                    ],
                    legalPersonIdCardNo: [
                        {required: true, message: '不能为空', trigger: 'blur'}
                    ],
                    legalPersonIdCardBeginDate: [
                        {required: true, message: '不能为空', trigger: 'change', type: 'date'}
                    ],
                    legalPersonIdCardFinalDate: [
                        {required: true, message: '不能为空', trigger: 'change', type: 'date'}
                    ],
                    shareholder: [
                        {required: true, message: '不能为空', trigger: 'blur'}
                    ],
                    accreditBizPerson: [
                        {required: true, message: '不能为空', trigger: 'blur'}
                    ],
                    accreditBizPersonIdCardNo: [
                        {required: true, message: '不能为空', trigger: 'blur'}
                    ],
                    accreditBizPersonIdCardBeginDate: [
                        {required: true, message: '不能为空', trigger: 'change', type: 'date'}
                    ],
                    accreditBizPersonIdCardFinalDate: [
                        {required: true, message: '不能为空', trigger: 'change', type: 'date'}
                    ],

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
                            '/merchGroup',
                            qs.stringify({
                                name: this.formValidate.name,
                                fullName: this.formValidate.fullName,
                                registerAddress: this.formValidate.registerAddress,
                                operateAddress: this.formValidate.operateAddress,
                                bizLicenseNo: this.formValidate.bizLicenseNo,
                                bizLicenseBeginDate: moment(this.formValidate.bizLicenseBeginDate).format("YYYYMMDDHHmmss"),
                                bizLicenseFinalDate: moment(this.formValidate.bizLicenseFinalDate).format("YYYYMMDDHHmmss"),
                                bizLicenseFileUrl: this.formValidate.bizLicenseFileUrl,
                                taxEnrolCertificateNo: this.formValidate.taxEnrolCertificateNo,
                                taxEnrolCertificateIssueDate: moment(this.formValidate.taxEnrolCertificateIssueDate).format("YYYYMMDDHHmmss"),
                                taxEnrolCertificateFileUrl: this.formValidate.taxEnrolCertificateFileUrl,
                                organizationCodeCertificateNo: this.formValidate.organizationCodeCertificateNo,
                                organizationCodeCertificateBeginDate: moment(this.formValidate.organizationCodeCertificateBeginDate).format("YYYYMMDDHHmmss"),
                                organizationCodeCertificateFinalDate: moment(this.formValidate.organizationCodeCertificateFinalDate).format("YYYYMMDDHHmmss"),
                                organizationCodeCertificateFileUrl: this.formValidate.organizationCodeCertificateFileUrl,
                                legalPerson: this.formValidate.legalPerson,
                                legalPersonIdCardNo: this.formValidate.legalPersonIdCardNo,
                                legalPersonIdCardBeginDate: moment(this.formValidate.legalPersonIdCardBeginDate).format("YYYYMMDDHHmmss"),
                                legalPersonIdCardFinalDate: moment(this.formValidate.legalPersonIdCardFinalDate).format("YYYYMMDDHHmmss"),
                                shareholder: this.formValidate.shareholder,
                                accreditBizPerson: this.formValidate.accreditBizPerson,
                                accreditBizPersonIdCardNo: this.formValidate.accreditBizPersonIdCardNo,
                                accreditBizPersonIdCardBeginDate: moment(this.formValidate.accreditBizPersonIdCardBeginDate).format("YYYYMMDDHHmmss"),
                                accreditBizPersonIdCardFinalDate: moment(this.formValidate.accreditBizPersonIdCardFinalDate).format("YYYYMMDDHHmmss"),
                                provinceNo: '000001'
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
