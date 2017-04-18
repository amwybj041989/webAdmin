<template>
    <div class="header">
        <div class="logo">趣看点后台管理系统</div>
        <div class="headerNav">
        	<!--<el-menu theme="dark" :default-active="1" class="" mode="horizontal" >
			  <el-menu-item index="1">运营管理</el-menu-item>
			  <el-menu-item index="2">内容管理</el-menu-item>
			  <el-menu-item index="4">用户中心</el-menu-item>
			  <el-menu-item index="3">数据中心</el-menu-item>
			  <el-menu-item index="3">系统配置</el-menu-item>
			</el-menu>-->
			<ul>
				<li class="headerNavLi">
					 <router-link to="/operation">运营管理</router-link>
				</li>
				<li class="headerNavLi">
					 <router-link to="/TaskDetail">内容管理</router-link>
				</li>
				<li class="headerNavLi">
					 <router-link to="/TaskDetail">用户中心</router-link>
				</li>
				<li class="headerNavLi">
					 <router-link to="/TaskDetail">数据统计</router-link>
				</li>
				<li class="headerNavLi">
					 <router-link to="/TaskDetail">系统配置</router-link>
				</li>
				
			</ul>
        </div>
        <div class="user-info">
            <el-dropdown trigger="click" @command="handleCommand">
                <span class="el-dropdown-link">
                    <img class="user-logo" src="../../../static/img/img.jpg">
                    {{username}}
                </span>
                <el-dropdown-menu slot="dropdown">
                    <el-dropdown-item command="loginout">退出</el-dropdown-item>
                </el-dropdown-menu>
            </el-dropdown>
        </div>
        
	    	
	   
    </div>
    
</template>

<script>
    export default {
        data() {
            return {
                name: 'linxin'
            }
        },
        computed:{
            username(){
                let username = localStorage.getItem('ms_username');
                return username ? username : this.name;
            }
        },
        methods:{
            handleCommand(command) {
                if(command == 'loginout'){
                    localStorage.removeItem('ms_username')
                    this.$router.push('/login');
                }
            }
        }
    }
</script>
<style scoped>
    .header {
        position: relative;
        box-sizing: border-box;
        width: 100%;
        height: 70px;
        font-size: 22px;
        line-height: 70px;
        color: #fff;
        background-color: #20A0FF;
        
    }
    .header .logo{
        float: left;
        width:250px;
        text-align: center;
    }
    .user-info {
        float: right;
        padding-right: 50px;
        font-size: 16px;
        color: #fff;
    }
    .user-info .el-dropdown-link{
        position: relative;
        display: inline-block;
        padding-left: 50px;
        color: #fff;
        cursor: pointer;
        vertical-align: middle;
    }
    .user-info .user-logo{
        position: absolute;
        left:0;
        top:15px;
        width:40px;
        height:40px;
        border-radius: 50%;
    }
    .el-dropdown-menu__item{
        text-align: center;
    }
    .headerNav{
    	position: absolute;
    	top: 0px;
    	left: 300px;
    	width: 40%;
    	height: 64px;
    }
    .headerNav ul{
    	display: flex;
    	width: 100%;
    	justify-content: space-between;
    }
    .headerNav ul li{
    	display: block;
    	height: 64px;
    	width: 20%;
    	color: #FFFFFF;
    	text-align: center;
    }
    .headerNavLi a{
    	display: block;
    	color: #FFFFFF;
    	height: 64px;
    	font-size: 18px;
    }
	.headerNavLi :hover{
		border-bottom: 6px #13CE66 solid;
		background-color: #50BFFF;
	}
</style>
