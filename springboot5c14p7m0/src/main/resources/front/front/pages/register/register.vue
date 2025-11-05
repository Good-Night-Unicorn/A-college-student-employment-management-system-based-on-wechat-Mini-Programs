<template>
<view class="content">
	<view class="box" :style='{"minHeight":"100%","padding":"60rpx","alignItems":"center","background":"url(http://codegen.caihongy.cn/20250222/87b074c3c23b4b738a1652e8b483d13b.png) no-repeat center bottom / 100% 100% ","display":"flex","width":"100%","justifyContent":"center","height":"auto"}'>
		<view :style='{"width":"100%","padding":"40rpx","position":"relative","borderRadius":"20rpx","background":"none","height":"auto"}'>
			<image :style='{"width":"160rpx","margin":"0 auto 24rpx auto","borderRadius":"8rpx","display":"none","height":"160rpx"}' src="http://codegen.caihongy.cn/20201114/7856ba26477849ea828f481fa2773a95.jpg" mode="aspectFill"></image>
			<view :style='{"border":"none","margin":"0 0 40rpx 0","alignItems":"center","flexWrap":"wrap","display":"flex","width":"100%","height":"auto"}' v-if="tableName=='xuesheng'" class="uni-form-item uni-column">
				<view :style='{"padding":"0 0 0 40rpx","color":"#000000","borderRadius":"0","textAlign":"left","background":"none","flex":"none","width":"100%","lineHeight":"50rpx","fontSize":"28rpx","height":"50rpx"}' class="label">学号：</view>
				<input :style='{"padding":"0px 24rpx","margin":"0px","borderColor":"#d0d0d0","color":"#000","borderRadius":"0","flex":"1","background":"none","borderWidth":"0 0 2rpx 0","fontSize":"28rpx","borderStyle":"solid","height":"80rpx"}'  v-model="ruleForm.xuehao"  type="text"  class="uni-input" name="" placeholder="学号" />
			</view>
			<view :style='{"border":"none","margin":"0 0 40rpx 0","alignItems":"center","flexWrap":"wrap","display":"flex","width":"100%","height":"auto"}' v-if="tableName=='xuesheng'" class="uni-form-item uni-column">
				<view :style='{"padding":"0 0 0 40rpx","color":"#000000","borderRadius":"0","textAlign":"left","background":"none","flex":"none","width":"100%","lineHeight":"50rpx","fontSize":"28rpx","height":"50rpx"}' class="label">密码：</view>
				<input :style='{"padding":"0px 24rpx","margin":"0px","borderColor":"#d0d0d0","color":"#000","borderRadius":"0","flex":"1","background":"none","borderWidth":"0 0 2rpx 0","fontSize":"28rpx","borderStyle":"solid","height":"80rpx"}'  v-model="ruleForm.mima" type="password"  class="uni-input" name="" placeholder="密码" />
			</view>
			<view :style='{"border":"none","margin":"0 0 40rpx 0","alignItems":"center","flexWrap":"wrap","display":"flex","width":"100%","height":"auto"}' v-if="tableName=='xuesheng'" class="uni-form-item uni-column">
				<view :style='{"padding":"0 0 0 40rpx","color":"#000000","borderRadius":"0","textAlign":"left","background":"none","flex":"none","width":"100%","lineHeight":"50rpx","fontSize":"28rpx","height":"50rpx"}' class="label">确认密码：</view>
				<input :style='{"padding":"0px 24rpx","margin":"0px","borderColor":"#d0d0d0","color":"#000","borderRadius":"0","flex":"1","background":"none","borderWidth":"0 0 2rpx 0","fontSize":"28rpx","borderStyle":"solid","height":"80rpx"}' v-model="ruleForm.mima2" type="password" class="uni-input" name="" placeholder="确认密码" />
			</view>
			<view :style='{"border":"none","margin":"0 0 40rpx 0","alignItems":"center","flexWrap":"wrap","display":"flex","width":"100%","height":"auto"}' v-if="tableName=='xuesheng'" class="uni-form-item uni-column">
				<view :style='{"padding":"0 0 0 40rpx","color":"#000000","borderRadius":"0","textAlign":"left","background":"none","flex":"none","width":"100%","lineHeight":"50rpx","fontSize":"28rpx","height":"50rpx"}' class="label">姓名：</view>
				<input :style='{"padding":"0px 24rpx","margin":"0px","borderColor":"#d0d0d0","color":"#000","borderRadius":"0","flex":"1","background":"none","borderWidth":"0 0 2rpx 0","fontSize":"28rpx","borderStyle":"solid","height":"80rpx"}'  v-model="ruleForm.xingming"  type="text"  class="uni-input" name="" placeholder="姓名" />
			</view>
            <view :style='{"border":"none","margin":"0 0 40rpx 0","alignItems":"center","flexWrap":"wrap","display":"flex","width":"100%","height":"auto"}' v-if="tableName=='xuesheng'" @tap="xueshengtouxiangTap" class="">
				<view :style='{"padding":"0 0 0 40rpx","color":"#000000","borderRadius":"0","textAlign":"left","background":"none","flex":"none","width":"100%","lineHeight":"50rpx","fontSize":"28rpx","height":"50rpx"}' class="label">头像：</view>
				<image :style='{"width":"120rpx","margin":"0 40rpx","borderRadius":"16rpx","display":"block","height":"120rpx"}' v-if="ruleForm.touxiang" class="avator" :src="baseUrl+ruleForm.touxiang" mode=""></image>
                <image :style='{"width":"120rpx","margin":"0 40rpx","borderRadius":"16rpx","display":"block","height":"120rpx"}' v-else class="avator" src="../../static/gen/upload.png" mode=""></image>
            </view>
            <view :style='{"border":"none","margin":"0 0 40rpx 0","alignItems":"center","flexWrap":"wrap","display":"flex","width":"100%","height":"auto"}' v-if="tableName=='xuesheng'" class="">
				<view :style='{"padding":"0 0 0 40rpx","color":"#000000","borderRadius":"0","textAlign":"left","background":"none","flex":"none","width":"100%","lineHeight":"50rpx","fontSize":"28rpx","height":"50rpx"}' class="label">性别：</view>
				<picker :style='{"width":"100%","margin":"0","display":"flex","height":"auto"}' v-if="tableName=='xuesheng'"  @change="xueshengxingbieChange" :value="xueshengxingbieIndex" :range="xueshengxingbieOptions">
					<view>
						<view :style='{"padding":"0 20rpx","borderColor":"#d0d0d0","color":"#74868B","flex":"1","borderWidth":"0 0 2rpx 0","lineHeight":"80rpx","fontSize":"28rpx","borderStyle":"solid"}' class="uni-input">{{ruleForm.xingbie?ruleForm.xingbie:"请选择性别"}}</view>
					</view>
				</picker>
			</view>
			<view :style='{"border":"none","margin":"0 0 40rpx 0","alignItems":"center","flexWrap":"wrap","display":"flex","width":"100%","height":"auto"}' v-if="tableName=='xuesheng'" class="uni-form-item uni-column">
				<view :style='{"padding":"0 0 0 40rpx","color":"#000000","borderRadius":"0","textAlign":"left","background":"none","flex":"none","width":"100%","lineHeight":"50rpx","fontSize":"28rpx","height":"50rpx"}' class="label">年龄：</view>
				<input :style='{"padding":"0px 24rpx","margin":"0px","borderColor":"#d0d0d0","color":"#000","borderRadius":"0","flex":"1","background":"none","borderWidth":"0 0 2rpx 0","fontSize":"28rpx","borderStyle":"solid","height":"80rpx"}'  v-model="ruleForm.nianling"  type="text"  class="uni-input" name="" placeholder="年龄" />
			</view>
			<view :style='{"border":"none","margin":"0 0 40rpx 0","alignItems":"center","flexWrap":"wrap","display":"flex","width":"100%","height":"auto"}' v-if="tableName=='xuesheng'" class="uni-form-item uni-column">
				<view :style='{"padding":"0 0 0 40rpx","color":"#000000","borderRadius":"0","textAlign":"left","background":"none","flex":"none","width":"100%","lineHeight":"50rpx","fontSize":"28rpx","height":"50rpx"}' class="label">邮箱：</view>
				<input :style='{"padding":"0px 24rpx","margin":"0px","borderColor":"#d0d0d0","color":"#000","borderRadius":"0","flex":"1","background":"none","borderWidth":"0 0 2rpx 0","fontSize":"28rpx","borderStyle":"solid","height":"80rpx"}'  v-model="ruleForm.youxiang"  type="text"  class="uni-input" name="" placeholder="邮箱" />
			</view>
			<view :style='{"border":"none","margin":"0 0 40rpx 0","alignItems":"center","flexWrap":"wrap","display":"flex","width":"100%","height":"auto"}' v-if="tableName=='xuesheng'" class="uni-form-item uni-column">
				<view :style='{"padding":"0 0 0 40rpx","color":"#000000","borderRadius":"0","textAlign":"left","background":"none","flex":"none","width":"100%","lineHeight":"50rpx","fontSize":"28rpx","height":"50rpx"}' class="label">手机：</view>
				<input :style='{"padding":"0px 24rpx","margin":"0px","borderColor":"#d0d0d0","color":"#000","borderRadius":"0","flex":"1","background":"none","borderWidth":"0 0 2rpx 0","fontSize":"28rpx","borderStyle":"solid","height":"80rpx"}'  v-model="ruleForm.shouji"  type="text"  class="uni-input" name="" placeholder="手机" />
			</view>
			<view :style='{"border":"none","margin":"0 0 40rpx 0","alignItems":"center","flexWrap":"wrap","display":"flex","width":"100%","height":"auto"}' v-if="tableName=='qiye'" class="uni-form-item uni-column">
				<view :style='{"padding":"0 0 0 40rpx","color":"#000000","borderRadius":"0","textAlign":"left","background":"none","flex":"none","width":"100%","lineHeight":"50rpx","fontSize":"28rpx","height":"50rpx"}' class="label">企业名称：</view>
				<input :style='{"padding":"0px 24rpx","margin":"0px","borderColor":"#d0d0d0","color":"#000","borderRadius":"0","flex":"1","background":"none","borderWidth":"0 0 2rpx 0","fontSize":"28rpx","borderStyle":"solid","height":"80rpx"}'  v-model="ruleForm.qiyemingcheng"  type="text"  class="uni-input" name="" placeholder="企业名称" />
			</view>
			<view :style='{"border":"none","margin":"0 0 40rpx 0","alignItems":"center","flexWrap":"wrap","display":"flex","width":"100%","height":"auto"}' v-if="tableName=='qiye'" class="uni-form-item uni-column">
				<view :style='{"padding":"0 0 0 40rpx","color":"#000000","borderRadius":"0","textAlign":"left","background":"none","flex":"none","width":"100%","lineHeight":"50rpx","fontSize":"28rpx","height":"50rpx"}' class="label">密码：</view>
				<input :style='{"padding":"0px 24rpx","margin":"0px","borderColor":"#d0d0d0","color":"#000","borderRadius":"0","flex":"1","background":"none","borderWidth":"0 0 2rpx 0","fontSize":"28rpx","borderStyle":"solid","height":"80rpx"}'  v-model="ruleForm.mima" type="password"  class="uni-input" name="" placeholder="密码" />
			</view>
			<view :style='{"border":"none","margin":"0 0 40rpx 0","alignItems":"center","flexWrap":"wrap","display":"flex","width":"100%","height":"auto"}' v-if="tableName=='qiye'" class="uni-form-item uni-column">
				<view :style='{"padding":"0 0 0 40rpx","color":"#000000","borderRadius":"0","textAlign":"left","background":"none","flex":"none","width":"100%","lineHeight":"50rpx","fontSize":"28rpx","height":"50rpx"}' class="label">确认密码：</view>
				<input :style='{"padding":"0px 24rpx","margin":"0px","borderColor":"#d0d0d0","color":"#000","borderRadius":"0","flex":"1","background":"none","borderWidth":"0 0 2rpx 0","fontSize":"28rpx","borderStyle":"solid","height":"80rpx"}' v-model="ruleForm.mima2" type="password" class="uni-input" name="" placeholder="确认密码" />
			</view>
			<view :style='{"border":"none","margin":"0 0 40rpx 0","alignItems":"center","flexWrap":"wrap","display":"flex","width":"100%","height":"auto"}' v-if="tableName=='qiye'" class="uni-form-item uni-column">
				<view :style='{"padding":"0 0 0 40rpx","color":"#000000","borderRadius":"0","textAlign":"left","background":"none","flex":"none","width":"100%","lineHeight":"50rpx","fontSize":"28rpx","height":"50rpx"}' class="label">负责人：</view>
				<input :style='{"padding":"0px 24rpx","margin":"0px","borderColor":"#d0d0d0","color":"#000","borderRadius":"0","flex":"1","background":"none","borderWidth":"0 0 2rpx 0","fontSize":"28rpx","borderStyle":"solid","height":"80rpx"}'  v-model="ruleForm.fuzeren"  type="text"  class="uni-input" name="" placeholder="负责人" />
			</view>
            <view :style='{"border":"none","margin":"0 0 40rpx 0","alignItems":"center","flexWrap":"wrap","display":"flex","width":"100%","height":"auto"}' v-if="tableName=='qiye'" @tap="qiyetouxiangTap" class="">
				<view :style='{"padding":"0 0 0 40rpx","color":"#000000","borderRadius":"0","textAlign":"left","background":"none","flex":"none","width":"100%","lineHeight":"50rpx","fontSize":"28rpx","height":"50rpx"}' class="label">LOGO：</view>
				<image :style='{"width":"120rpx","margin":"0 40rpx","borderRadius":"16rpx","display":"block","height":"120rpx"}' v-if="ruleForm.touxiang" class="avator" :src="baseUrl+ruleForm.touxiang" mode=""></image>
                <image :style='{"width":"120rpx","margin":"0 40rpx","borderRadius":"16rpx","display":"block","height":"120rpx"}' v-else class="avator" src="../../static/gen/upload.png" mode=""></image>
            </view>
            <view :style='{"border":"none","margin":"0 0 40rpx 0","alignItems":"center","flexWrap":"wrap","display":"flex","width":"100%","height":"auto"}' v-if="tableName=='qiye'" class="">
				<view :style='{"padding":"0 0 0 40rpx","color":"#000000","borderRadius":"0","textAlign":"left","background":"none","flex":"none","width":"100%","lineHeight":"50rpx","fontSize":"28rpx","height":"50rpx"}' class="label">性别：</view>
				<picker :style='{"width":"100%","margin":"0","display":"flex","height":"auto"}' v-if="tableName=='qiye'"  @change="qiyexingbieChange" :value="qiyexingbieIndex" :range="qiyexingbieOptions">
					<view>
						<view :style='{"padding":"0 20rpx","borderColor":"#d0d0d0","color":"#74868B","flex":"1","borderWidth":"0 0 2rpx 0","lineHeight":"80rpx","fontSize":"28rpx","borderStyle":"solid"}' class="uni-input">{{ruleForm.xingbie?ruleForm.xingbie:"请选择性别"}}</view>
					</view>
				</picker>
			</view>
            <view :style='{"border":"none","margin":"0 0 40rpx 0","alignItems":"center","flexWrap":"wrap","display":"flex","width":"100%","height":"auto"}' v-if="tableName=='qiye'" @tap="qiyezizhizhengshuTap" class="">
				<view :style='{"padding":"0 0 0 40rpx","color":"#000000","borderRadius":"0","textAlign":"left","background":"none","flex":"none","width":"100%","lineHeight":"50rpx","fontSize":"28rpx","height":"50rpx"}' class="label">资质证书：</view>
				<input :style='{"padding":"0px 24rpx","margin":"0px","borderColor":"#d0d0d0","color":"#000","borderRadius":"0","flex":"1","background":"none","borderWidth":"0 0 2rpx 0","fontSize":"28rpx","borderStyle":"solid","height":"80rpx"}' v-if="ruleForm.zizhizhengshu"  v-model="baseUrl+ruleForm.zizhizhengshu" placeholder="资质证书"></input>
                <image :style='{"width":"120rpx","margin":"0 40rpx","borderRadius":"16rpx","display":"block","height":"120rpx"}' v-else class="avator" src="../../static/gen/upload.png" mode=""></image>
            </view>
			<view :style='{"border":"none","margin":"0 0 40rpx 0","alignItems":"center","flexWrap":"wrap","display":"flex","width":"100%","height":"auto"}' v-if="tableName=='qiye'" class="uni-form-item uni-column">
				<view :style='{"padding":"0 0 0 40rpx","color":"#000000","borderRadius":"0","textAlign":"left","background":"none","flex":"none","width":"100%","lineHeight":"50rpx","fontSize":"28rpx","height":"50rpx"}' class="label">企业地址：</view>
				<input :style='{"padding":"0px 24rpx","margin":"0px","borderColor":"#d0d0d0","color":"#000","borderRadius":"0","flex":"1","background":"none","borderWidth":"0 0 2rpx 0","fontSize":"28rpx","borderStyle":"solid","height":"80rpx"}'  v-model="ruleForm.qiyedizhi"  type="text"  class="uni-input" name="" placeholder="企业地址" />
			</view>
			<view :style='{"border":"none","margin":"0 0 40rpx 0","alignItems":"center","flexWrap":"wrap","display":"flex","width":"100%","height":"auto"}' v-if="tableName=='qiye'" class="uni-form-item uni-column">
				<view :style='{"padding":"0 0 0 40rpx","color":"#000000","borderRadius":"0","textAlign":"left","background":"none","flex":"none","width":"100%","lineHeight":"50rpx","fontSize":"28rpx","height":"50rpx"}' class="label">邮箱：</view>
				<input :style='{"padding":"0px 24rpx","margin":"0px","borderColor":"#d0d0d0","color":"#000","borderRadius":"0","flex":"1","background":"none","borderWidth":"0 0 2rpx 0","fontSize":"28rpx","borderStyle":"solid","height":"80rpx"}'  v-model="ruleForm.youxiang"  type="text"  class="uni-input" name="" placeholder="邮箱" />
			</view>
			<view :style='{"border":"none","margin":"0 0 40rpx 0","alignItems":"center","flexWrap":"wrap","display":"flex","width":"100%","height":"auto"}' v-if="tableName=='qiye'" class="uni-form-item uni-column">
				<view :style='{"padding":"0 0 0 40rpx","color":"#000000","borderRadius":"0","textAlign":"left","background":"none","flex":"none","width":"100%","lineHeight":"50rpx","fontSize":"28rpx","height":"50rpx"}' class="label">联系电话：</view>
				<input :style='{"padding":"0px 24rpx","margin":"0px","borderColor":"#d0d0d0","color":"#000","borderRadius":"0","flex":"1","background":"none","borderWidth":"0 0 2rpx 0","fontSize":"28rpx","borderStyle":"solid","height":"80rpx"}'  v-model="ruleForm.lianxidianhua"  type="text"  class="uni-input" name="" placeholder="联系电话" />
			</view>
			<button :style='{"border":"0","padding":"0px","margin":"0 0 24rpx 0","color":"#fff","borderRadius":"8rpx","background":"linear-gradient(45deg, #3d4e81, #5753c9, #6e7ff3)","width":"100%","lineHeight":"80rpx","fontSize":"32rpx","fontWeight":"600","height":"80rpx"}' class="btn-submit" @tap="register" type="primary">注册</button>
			
			<view class="idea1" :style='{"width":"100%","background":"red","display":"none","height":"80rpx"}'>idea1</view>
			<view class="idea2" :style='{"width":"100%","background":"red","display":"none","height":"80rpx"}'>idea2</view>
			<view class="idea3" :style='{"width":"100%","background":"red","display":"none","height":"80rpx"}'>idea3</view>
		</view>
	</view>
</view>
</template>

<script>
    import multipleSelect from "@/components/momo-multipleSelect/momo-multipleSelect";
	export default {
		data() {
			return {
                xueshengxingbieOptions: [],
                xueshengxingbieIndex: 0,
                qiyexingbieOptions: [],
                qiyexingbieIndex: 0,
				ruleForm: {
                xuehao: '',
                mima: '',
                xingming: '',
                touxiang: '',
                xingbie: '',
                nianling: '',
                youxiang: '',
                shouji: '',
                qiyemingcheng: '',
                mima: '',
                fuzeren: '',
                touxiang: '',
                xingbie: '',
                zizhizhengshu: '',
                qiyedizhi: '',
                youxiang: '',
                lianxidianhua: '',
                shhf: '',
				},
				tableName:""
			}
		},
        components: {
            multipleSelect
        },
        computed: {
            baseUrl() {
                return this.$base.url;
            },
        },
		async onLoad() {
			let res = [];
			let table = uni.getStorageSync("loginTable");
            this.tableName = table;

                        // 自定义下拉框值
			if(this.tableName=='xuesheng'){
                this.xueshengxingbieOptions = "男,女".split(',');
				this.ruleForm.xingbie=this.xueshengxingbieOptions[0]
			}
                        // 自定义下拉框值
			if(this.tableName=='qiye'){
                this.qiyexingbieOptions = "男,女".split(',');
				this.ruleForm.xingbie=this.qiyexingbieOptions[0]
			}
			
			this.styleChange()
		},
		methods: {

            xueshengtouxiangTap() {
                let _this = this;
                this.$api.upload(function(res) {
                    _this.ruleForm.touxiang = 'upload/' + res.file;
					_this.$forceUpdate();
                });
            },
            // 下拉变化
            xueshengxingbieChange(e) {
                    this.xueshengxingbieIndex = e.target.value
                    this.ruleForm.xingbie = this.xueshengxingbieOptions[this.xueshengxingbieIndex]
            },
            qiyetouxiangTap() {
                let _this = this;
                this.$api.upload(function(res) {
                    _this.ruleForm.touxiang = 'upload/' + res.file;
					_this.$forceUpdate();
                });
            },
            // 下拉变化
            qiyexingbieChange(e) {
                    this.qiyexingbieIndex = e.target.value
                    this.ruleForm.xingbie = this.qiyexingbieOptions[this.qiyexingbieIndex]
            },
            qiyezizhizhengshuTap() {
                let _this = this;
                this.$api.upload(function(res) {
                    _this.ruleForm.zizhizhengshu = 'upload/' + res.file;
					_this.$forceUpdate();
                });
            },

            toggleTab(str) {
                this.$refs[str].show();
            },

			styleChange() {
				this.$nextTick(()=>{
					// document.querySelectorAll('.uni-input .uni-input-input').forEach(el=>{
					//   el.style.backgroundColor = this.registerFrom.content.input.backgroundColor
					// })
				})
			},
			// 获取uuid
			getUUID () {
				return new Date().getTime();
			},
			// 注册
			async register() {
				
				if((!this.ruleForm.xuehao) && `xuesheng` == this.tableName){
					this.$utils.msg(`学号不能为空`);
					return
				}
				if((!this.ruleForm.mima) && `xuesheng` == this.tableName){
					this.$utils.msg(`密码不能为空`);
					return
				}
                if(`xuesheng` == this.tableName && (this.ruleForm.mima!=this.ruleForm.mima2)){
                    this.$utils.msg(`两次密码输入不一致`);
                    return
                }
				if((!this.ruleForm.xingming) && `xuesheng` == this.tableName){
					this.$utils.msg(`姓名不能为空`);
					return
				}
				if((!this.ruleForm.touxiang) && `xuesheng` == this.tableName){
					this.$utils.msg(`头像不能为空`);
					return
				}
				if((!this.ruleForm.nianling) && `xuesheng` == this.tableName){
					this.$utils.msg(`年龄不能为空`);
					return
				}
				if(`xuesheng` == this.tableName && this.ruleForm.nianling&&(!this.$validate.isIntNumer(this.ruleForm.nianling))){
					this.$utils.msg(`年龄应输入整数`);
					return
				}
				if((!this.ruleForm.youxiang) && `xuesheng` == this.tableName){
					this.$utils.msg(`邮箱不能为空`);
					return
				}
				if(`xuesheng` == this.tableName && this.ruleForm.youxiang&&(!this.$validate.isEmail(this.ruleForm.youxiang))){
					this.$utils.msg(`邮箱应输入邮件格式`);
					return
				}
				if((!this.ruleForm.shouji) && `xuesheng` == this.tableName){
					this.$utils.msg(`手机不能为空`);
					return
				}
				if(`xuesheng` == this.tableName && this.ruleForm.shouji&&(!this.$validate.isMobile(this.ruleForm.shouji))){
					this.$utils.msg(`手机应输入手机格式`);
					return
				}
				if((!this.ruleForm.qiyemingcheng) && `qiye` == this.tableName){
					this.$utils.msg(`企业名称不能为空`);
					return
				}
				if((!this.ruleForm.mima) && `qiye` == this.tableName){
					this.$utils.msg(`密码不能为空`);
					return
				}
                if(`qiye` == this.tableName && (this.ruleForm.mima!=this.ruleForm.mima2)){
                    this.$utils.msg(`两次密码输入不一致`);
                    return
                }
				if((!this.ruleForm.fuzeren) && `qiye` == this.tableName){
					this.$utils.msg(`负责人不能为空`);
					return
				}
				if((!this.ruleForm.touxiang) && `qiye` == this.tableName){
					this.$utils.msg(`LOGO不能为空`);
					return
				}
				if(`qiye` == this.tableName && this.ruleForm.youxiang&&(!this.$validate.isEmail(this.ruleForm.youxiang))){
					this.$utils.msg(`邮箱应输入邮件格式`);
					return
				}
				if(`qiye` == this.tableName && this.ruleForm.lianxidianhua&&(!this.$validate.isMobile(this.ruleForm.lianxidianhua))){
					this.$utils.msg(`联系电话应输入手机格式`);
					return
				}
				await this.$api.register(`${this.tableName}`, this.ruleForm);
				this.$utils.msgBack('注册成功');;
			}
		}
	}
</script>

<style lang="scss" scoped>
	.content {
		min-height: calc(100vh - 44px);
		box-sizing: border-box;
	}
</style>
