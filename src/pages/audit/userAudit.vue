<template>
    <div class="user-audit-pages">
        <tablelist ref="tableList"
                   :page-title="'用户审核'"
                   :search-title="'用户审核搜索条件'"
                   :form="form"
                   :data="[{sort:'2',id:'22',nickname:'张张',identify:'321563258963145',applyTime:'2018-07-15 19:21',headPic:'../assets/images/056f814a17e86151a306028bee30add4.png'},
                           {sort:'3',id:'26',nickname:'张张',identify:'321563258963145',applyTime:'2018-07-15 19:21',headPic:'../assets/images/056f814a17e86151a306028bee30add4.png'}]"
                   :search-param="[{label:'用户昵称',prop:'nickname'},
                                   {label:'用户ID',prop:'id'},
                                   {label:'身份证号',prop:'identify'},
                                   {label:'审核状态',prop:'status',type:'select',options:[{value:1,name:'待审核'}]},
                                   {label:'提交时间',prop:'time',type:'dataPicker'}]"
                   :button-group="[{label:'查询',methods:'search'},
                                   {label:'批量通过',methods:'agree'},
                                   {label:'批量拒绝',methods:'refuse'}]"
                   :table-type="[{label:'序号',prop:'sort',minWidth:80},
                                 {label:'用户ID',prop:'id',minWidth:80},
                                 {label:'昵称',prop:'nickname',minWidth:80},
                                 {label:'身份证号码',prop:'identify',minWidth:140},
                                 {label:'申请时间',prop:'applyTime',minWidth:140},
                                 {label:'身份证头像',prop:'headPic',type:'img',minWidth:140}]"
                   :table-option="[{label:'通过',methods:'agree',span:5},
                                   {label:'拒绝',methods:'refuse',type:'danger',span:5}]"
                   :table-option-width="150"
                   @getData="getData"
                   @handleButton="handleButton" 
                   @handleTableButton="handleTableButton"/>
    </div>
</template>
<script>
import tablelist from '../../components/tableList.vue'
export default{
    components:{
        tablelist
    },
    data(){
        return{
            form:{
                nickname:'',
                id:'',
                identify:'',
                status:'',
                time:''
            }
        }
    },
    methods:{
        getData(){
            this.$message.success('get data')
        },
        handleButton(val){
            this.$message.info(val)
        },
        handleTableButton(val){
            this.$message.success(val)
        }
    }
} 
</script>
