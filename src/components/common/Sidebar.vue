<template>
    <div class="sidebar">
        <!--<el-menu :default-active="onRoutes" class="el-menu-vertical-demo" theme="dark" unique-opened router>
            <el-menu-item index="readme">
                	仪表盘
            </el-menu-item>
            <el-menu mode="vertical" default-active="1" class="el-menu-vertical-demo" theme="dark">
		      <el-menu-item-group title="文章管理" style="background-color: #58B7FF;">
		         <router-link to="/FinishTaskInfo">Go to Foo</router-link>
		        <el-menu-item index="2">原创文章</el-menu-item>
		        <el-menu-item index="3">待发布文章</el-menu-item>
		        <el-menu-item index="4">待审核文章</el-menu-item>
		        <el-menu-item index="5">已删除文章</el-menu-item>
		        <el-menu-item index="6">按地址采集文章</el-menu-item>
		        <el-menu-item index="17">生成静态文件</el-menu-item>
		      </el-menu-item-group>
		      <el-menu-item-group title="视频管理">
		        <el-menu-item index="3">在线视频列表</el-menu-item>
		        <el-menu-item index="3">待发布视频</el-menu-item>
		        <el-menu-item index="4">待审核视频</el-menu-item>
		        <el-menu-item index="5">已删除视频</el-menu-item>
		        <el-menu-item index="6">按地址采集视频</el-menu-item>
		      </el-menu-item-group>
		      <el-menu-item-group title="组长审核">
		        <el-menu-item index="3">推送审核</el-menu-item>
		 
		        
		      </el-menu-item-group>
		      <el-menu-item-group title="推送内容">
		        <el-menu-item index="3">推送文章</el-menu-item>
		         <el-menu-item index="3">推送视频</el-menu-item>
		 
		        
		      </el-menu-item-group>
		      <el-menu-item-group title="文章采集管理">
		        <el-menu-item index="3">采集网站</el-menu-item>
		         <el-menu-item index="3">采集RSS</el-menu-item>
		 
		        
		      </el-menu-item-group>
		      <el-menu-item-group title="视频采集管理">
		        <el-menu-item index="3">采集网站</el-menu-item>
		 
		        
		      </el-menu-item-group>
		      
		    </el-menu>
            <el-submenu index="3">
                <template slot="title"><i class="el-icon-date"></i>Map地图</template>
                <el-menu-item index="baseform">基本表单</el-menu-item>
                <el-menu-item index="vueeditor">编辑器</el-menu-item>
                <el-menu-item index="markdown">markdown</el-menu-item>
                <el-menu-item index="upload">文件上传</el-menu-item>
            </el-submenu>
            <el-submenu index="4">
                <template slot="title"><i class="el-icon-star-on"></i>人员信息管理</template>
                <el-menu-item index="inspectorInfo">巡检员信息</el-menu-item>
                <el-menu-item index="mine">个人资料</el-menu-item>
            </el-submenu>
        </el-menu>-->
       <router-view></router-view>
    </div>
</template>
<script>
    export default {
        computed:{
            onRoutes(){
                return this.$route.path.replace('/','');
            }
        }
    }
</script>
<style scoped>
    .sidebar{
        display: block;
        position: absolute;
        width: 180px;
        left: 0;
        top: 70px;
        bottom:0;
        background: #20A0FF;
    }
    
</style>
