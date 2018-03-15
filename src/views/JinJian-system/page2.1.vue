<style lang="less">
    @import '../../styles/common.less';
    @import 'less/page1.1.less';
</style>

<template>
    <div class="jinjian-page">
        <Form ref="formValidate" :model="formValidate" :rules="ruleValidate" label-position="top">
            <Card>
                <p slot="title">
                    新增门店医院
                </p>
                <Row class="my-row" :gutter="16" type="flex" align="middle">
                    <Col span="12">
                    <FormItem label="选择医疗集团" prop="merchGroupId">
                        <Select v-model="formValidate.merchGroupId">
                            <Option v-for="item in merchGroupList"
                                    :value="item.id" :key="item.id">
                                {{ item.fullName }}
                            </Option>
                        </Select>
                    </FormItem>
                    </Col>
                    <Col span="12">
                    <FormItem label="选择支付渠道" prop="payChannelId">
                        <Select v-model="formValidate.payChannelId">
                            <Option v-for="item in payChannelList"
                                    :value="item.id" :key="item.id">
                                {{ item.fullName }}
                            </Option>
                        </Select>
                    </FormItem>
                    </Col>
                </Row>
                <Row class="my-row" :gutter="16" type="flex" align="middle">
                    <Col span="12">
                    <FormItem label="商户简称" prop="name">

                        <Input v-model="formValidate.name" placeholder="Enter something..."></Input>
                    </FormItem>
                    </Col>
                    <Col span="12">
                    <FormItem label="商户全称" prop="fullName">

                        <Input v-model="formValidate.fullName" placeholder="Enter something..."></Input>
                    </FormItem>
                    </Col>
                </Row>
                <Row class="my-row" :gutter="16" type="flex" align="middle">
                    <Col span="12">
                    <FormItem label="外部关联商户编号" prop="outMerchantNo">

                        <Input v-model="formValidate.outMerchantNo" placeholder="Enter something..."></Input>
                    </FormItem>
                    </Col>
                    <Col span="12">
                    <FormItem label="约定商户编号" prop="merchantNo">

                        <Input v-model="formValidate.merchantNo" placeholder="Enter something..."></Input>
                    </FormItem>
                    </Col>
                </Row>
                <Row class="my-row" :gutter="16" type="flex" align="middle">
                    <Col span="12">
                    <FormItem label="联系人" prop="linkman">

                        <Input v-model="formValidate.linkman" placeholder="Enter something..."></Input>
                    </FormItem>
                    </Col>
                    <Col span="12">
                    <FormItem label="联系电话" prop="linkphone">
                        <Input v-model="formValidate.linkphone" placeholder="Enter something..."></Input>
                    </FormItem>
                    </Col>
                </Row>
                <!--   <div class="line-gray"></div>

                   <Row class="my-row" :gutter="16" type="flex" align="middle">
                       <Col span="6">
                       <p>地址</p>
                       </Col>
                       <Col span="6">
                       <div>
                           <div class="ivu-card-body"> <div><div class="ivu-row" style="margin-right: -5px;"><div class="ivu-col ivu-col-span-8" style=" padding-right: 5px;"><div class="ivu-select ivu-select-single ivu-select-default" style="width: 100%;"><div class="ivu-select-selection"><input type="hidden">  <span class="ivu-select-placeholder">请选择省</span> <span class="ivu-select-selected-value" style="display: none;"></span> &lt;!&ndash;&ndash;&gt; <i class="ivu-icon ivu-icon-ios-close ivu-select-arrow" style="display: none;"></i> <i class="ivu-icon ivu-icon-arrow-down-b ivu-select-arrow"></i></div> &lt;!&ndash;&ndash;&gt;</div></div> <div class="ivu-col ivu-col-span-8" style="padding-left: 5px; padding-right: 5px;"><div class="ivu-select ivu-select-single ivu-select-default" style="width: 100%;"><div class="ivu-select-selection"><input type="hidden">  <span class="ivu-select-placeholder">请选择市</span> <span class="ivu-select-selected-value" style="display: none;"></span> &lt;!&ndash;&ndash;&gt; <i class="ivu-icon ivu-icon-ios-close ivu-select-arrow" style="display: none;"></i> <i class="ivu-icon ivu-icon-arrow-down-b ivu-select-arrow"></i></div> &lt;!&ndash;&ndash;&gt;</div></div> <div class="ivu-col ivu-col-span-8" style="padding-left: 5px; padding-right: 5px;"><div class="ivu-select ivu-select-single ivu-select-default" style="width: 100%;"><div class="ivu-select-selection"><input type="hidden">  <span class="ivu-select-placeholder">请选择县区</span> <span class="ivu-select-selected-value" style="display: none;"></span> &lt;!&ndash;&ndash;&gt; <i class="ivu-icon ivu-icon-ios-close ivu-select-arrow" style="display: none;"></i> <i class="ivu-icon ivu-icon-arrow-down-b ivu-select-arrow"></i></div> &lt;!&ndash;&ndash;&gt;</div></div> &lt;!&ndash;&ndash;&gt;</div> </div></div>
                          &lt;!&ndash; <div class="ivu-row" style="margin-left: -5px; margin-right: -5px;">
                               <div class="ivu-col ivu-col-span-6" style="padding-left: 5px; padding-right: 5px;">
                                   <div class="ivu-select ivu-select-single ivu-select-default" style="width: 100%;">
                                       <div class="ivu-select-selection"><input type="hidden" value="河北省">
                                           <span class="ivu-select-placeholder" style="display: none;">请选择省</span>
                                           <span class="ivu-select-selected-value" style="">河北省</span> &lt;!&ndash;&ndash;&gt;
                                           <i class="ivu-icon ivu-icon-ios-close ivu-select-arrow" style="display: none;"></i>
                                           <i class="ivu-icon ivu-icon-arrow-down-b ivu-select-arrow"></i>
                                       </div> &lt;!&ndash;&ndash;&gt;
                                   </div>
                               </div>
                               <div class="ivu-col ivu-col-span-6" style="padding-left: 5px; padding-right: 5px;">
                               <div class="ivu-select ivu-select-single ivu-select-default" style="width: 100%;">
                                   <div class="ivu-select-selection"><input type="hidden" value="张家口市">
                                       <span class="ivu-select-placeholder" style="display: none;">请选择市</span>
                                       <span class="ivu-select-selected-value" style="">张家口市</span> &lt;!&ndash;&ndash;&gt;
                                       <i class="ivu-icon ivu-icon-ios-close ivu-select-arrow" style="display: none;"></i>
                                       <i class="ivu-icon ivu-icon-arrow-down-b ivu-select-arrow"></i>
                                   </div> &lt;!&ndash;&ndash;&gt;</div></div> <div class="ivu-col ivu-col-span-6" style="padding-left: 5px; padding-right: 5px;">
                               <div class="ivu-select ivu-select-single ivu-select-default" style="width: 100%;">
                                   <div class="ivu-select-selection"><input type="hidden" value="怀来县">
                                       <span class="ivu-select-placeholder" style="display: none;">请选择县区</span>
                                       <span class="ivu-select-selected-value" style="">怀来县</span> &lt;!&ndash;&ndash;&gt;
                                       <i class="ivu-icon ivu-icon-ios-close ivu-select-arrow" style="display: none;"></i>
                                       <i class="ivu-icon ivu-icon-arrow-down-b ivu-select-arrow"></i></div> &lt;!&ndash;&ndash;&gt;
                               </div>
                           </div>
                               <div class="ivu-col ivu-col-span-6" style="padding-left: 5px; padding-right: 5px;">
                                   <div class="ivu-select ivu-select-single ivu-select-default" style="width: 100%;">
                                       <div class="ivu-select-selection"><input type="hidden" value="沙城镇">
                                           <span class="ivu-select-placeholder" style="display: none;">请选择乡镇街</span>
                                           <span class="ivu-select-selected-value" style="">沙城镇</span> &lt;!&ndash;&ndash;&gt;
                                           <i class="ivu-icon ivu-icon-ios-close ivu-select-arrow" style="display: none;"></i>
                                           <i class="ivu-icon ivu-icon-arrow-down-b ivu-select-arrow"></i>
                                       </div> &lt;!&ndash;&ndash;&gt;
                                   </div>
                               </div>
                           </div>&ndash;&gt;
                       </div>
                       </Col>
                   </Row>-->
                <!--   <Row class="my-row" :gutter="16" type="flex" align="middle">
                       <Col span="6">
                       <p>输入详细地址</p>
                       </Col>
                       <Col span="6">
                       <Input  placeholder="Enter something..."></Input>
                       </Col>
                       <Col span="6">
                       <button type="button" class="ivu-btn ivu-btn-primary ivu-btn-sm">
                           <span>地图标注</span>
                       </button>
                       </Col>
                   </Row>-->
            </Card>
            <!--   <Card>
                   <p slot="title">
                       门店医院账户
                   </p>
                   <Row class="my-row" :gutter="16" type="flex" align="middle">
                       <Col span="6">
                       <p slot="title">门店医院账户</p>

                       </Col>

                       <Col span="6">
                       <CheckboxGroup>
                           <Checkbox label="使用公司账号"></Checkbox>
                           <Checkbox label="自建帐号"></Checkbox>
                       </CheckboxGroup>

                       </Col>
                   </Row>
                   <Row class="my-row" :gutter="16" type="flex" align="middle">
                       <Col span="6">
                       <p>用户名称</p>
                       </Col>
                       <Col span="6">
                       <Input  placeholder="Enter something..."></Input>
                       </Col>
                       <Col span="6">
                       <p>帐号</p>
                       </Col>
                       <Col span="6">
                       <Input placeholder="Enter something..."></Input>
                       </Col>
                   </Row>
                   <Row class="my-row" :gutter="16" type="flex" align="middle">
                       <Col span="6">
                       <p>开户银行</p>
                       </Col>
                       <Col span="6">
                       <Input  placeholder="Enter something..."></Input>
                       </Col>
                       <Col span="6">
                       <p>联行号</p>
                       </Col>
                       <Col span="6">
                       <Input placeholder="Enter something..."></Input>
                       </Col>
                   </Row>
               </Card>-->
        </Form>
        <Button class="margin-top-10" type="primary" @click="submit('formValidate')">保存</Button>

    </div>
</template>

<script>
    import qs from 'qs';

    export default {
        data () {
            return {
                merchGroupList: [],
                payChannelList: [],
                formValidate: {
                    merchGroupId: '',
                    payChannelId: '',
                    name: '',
                    fullName: '',
                    linkman: '',
                    linkphone: '',
                    outMerchantNo: '',
                    merchantNo: '',
                },
                ruleValidate: {
                    merchGroupId: [
                        {required: true, message: '不能为空', trigger: 'change'}
                    ],
                    payChannelId: [
                        {required: true, message: '不能为空', trigger: 'change'}
                    ],
                    name: [
                        {required: true, message: '不能为空', trigger: 'blur'}
                    ],
                    fullName: [
                        {required: true, message: '不能为空', trigger: 'blur'}
                    ],
                    linkman: [
                        {required: true, message: '不能为空', trigger: 'blur'}
                    ],
                    linkphone: [
                        {required: true, message: '不能为空', trigger: 'blur'}
                    ],
                    outMerchantNo: [
                        {required: true, message: '不能为空', trigger: 'blur'}
                    ],
                    merchantNo: [
                        {required: true, message: '不能为空', trigger: 'blur'}
                    ],
                }
            };
        },
        methods: {
            //获取医疗集团列表
            getMerchGroups(){
                this.$http.get(
                    '/merchGroups',
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
                            this.formValidate.merchGroupList = []; // 清空列表
                            if (res.data.payload.totalRecord > 0) {
                                res.data.payload.items.forEach((item, i) => {
                                    this.formValidate.merchGroupList.push(item);
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
            //获取支付渠道列表
            getPayChannel(){
                this.$http.get(
                    '/paychannels',
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
                            this.formValidate.payChannelList = []; // 清空表格
                            if (res.data.payload.totalRecord > 0) {
                                res.data.payload.items.forEach((item, i) => {
                                    this.formValidate.payChannelList.push(item);
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
                            '/merchant',
                            qs.stringify({
                                merchGroupId: this.formValidate.merchGroupId,
                                payChannelId: this.formValidate.payChannelId,
                                name: this.formValidate.name,
                                fullName: this.formValidate.fullName,
                                linkman: this.formValidate.linkman,
                                linkphone: this.formValidate.linkphone,
                                outMerchantNo: this.formValidate.outMerchantNo,
                                merchantNo: this.formValidate.merchantNo,
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
            this.getPayChannel();
            this.getMerchGroups();
        }
    };
</script>
