<template>
    <div class="table">
       1111111111111111
    </div>
</template>

<script>
    export default {
        data() {
            return {
                multipleSelection:[],
                tableData: [{
                    id:"17001",
                    taskName: 'ydc201211',
                    overTime: '2017.3.14',
                    inspectorName: '张三',
                    priority: '1'
                }, 
                {
                    id:"17002",
                    taskName: 'ydc201211',
                    overTime: '2016.11.11',
                    inspectorName: '张三',
                    priority: '1'
                }, 
                {
                    id:"17003",
                    taskName: 'ydc201211',
                    overTime: '2016.11.11',
                    inspectorName: '张三',
                    priority: '1'
                }, 
                {
                    id:"17004",
                    taskName: 'ydc201211',
                    overTime: '2016.11.11',
                    inspectorName: '张三',
                    priority: '1'
                }],

                isCustomDelete:0
            }
        },
        components:{
    
        },
        methods: {
            formatter(row, column) {
                return row.inspectorName;
            },
            filterTag(value, row) {
                return row.tag === value;
            },
            showDetail(index,row){
                 this.$router.push({ 
                    path: '/taskDetail', 
                    query: { 
                        type:'detail', 
                        id:row.id
                    }
                });
            },
            handleDelete(index, row) {
                this.$confirm('此操作将永久删除该信息, 是否继续?', '提示', {
                    confirmButtonText: '确定',
                    cancelButtonText: '取消',
                    type: 'warning'
                    }).then(() => {
                        

                        this.$message({
                            type: 'success',
                            message: '删除成功!'
                        });
                        this.tableData.splice(index,1);
                    }).catch(() => {
                        this.$message({
                            type: 'info',
                            message: '已取消删除'
                        });          
                });
                // this.$message.error('删除第'+(index+1)+'行');
            },
            handleAdd(){
                 this.$router.push({ 
                    path: '/handleTask',
                    query: { 
                        type:'add'
                    }
                });
            },

            handleSelectionChange(val) {
                if(val.length != 0){
                    this.isCustomDelete = 1;
                    this.multipleSelection = val;
                }else{
                    this.isCustomDelete = 0;
                }
            },
            customDelete(){
                this.$confirm('此操作将永久删除该信息, 是否继续?', '提示', {
                    confirmButtonText: '确定',
                    cancelButtonText: '取消',
                    type: 'warning'
                    }).then(() => {
                        for(var i in this.multipleSelection){
                            for(var j in this.tableData){
                                if(this.multipleSelection[i].id === this.tableData[j].id){
                                    this.tableData.splice(j,1);
                                }
                            }
                        }
                        this.$message({
                            type: 'success',
                            message: '删除成功!'
                        });
                    }).catch(() => {
                        this.$message({
                            type: 'info',
                            message: '已取消删除'
                    });          
                });
            }

            
        }
    }
</script>
<style>
    .add-btn{
        float: left;
        margin: 10px 0 0 0;
    }
    .detail-cell:hover{
        color: #0099FF;
        cursor: pointer;
    }
     .custom-delete{
        margin-bottom: 10px;
        height: 30px;
    }
</style>