<!--  -->
<template>
  <div>
    <el-row>
      <el-table class="homeTableA" :data="tableData" border style="width:1340px" height="622px">
        <el-table-column width="300" prop="val1" align="center" label="商品"></el-table-column>
        <el-table-column prop="val2" align="center" label="单价/数量"></el-table-column>
        <el-table-column prop="val3" align="center" label="发型师/助理"></el-table-column>
        <el-table-column prop="val4" align="center" label="用户"></el-table-column>
        <el-table-column prop="val9" align="center" label="支付方式"></el-table-column>
        <el-table-column width="220" prop="val5" align="center" label="订单总额/优惠金额/实付金额"></el-table-column>
        <el-table-column width="140" prop="val7" align="center" label="预约时间"></el-table-column>
        <el-table-column width="140" prop="val8" align="center" label="完成时间"></el-table-column>
      </el-table>
    </el-row>
    <br />
    <div class="eltablebox">
      <el-table class="homeTableA" :data="tableData" border style="width:1340px" height="672px">
        <el-table-column width="50" type="index" align="center" label="序号"></el-table-column>
        <el-table-column width="200" prop="val1" align="center" label="预约号"></el-table-column>
        <el-table-column prop="val2" align="center" label="预约项目"></el-table-column>
        <el-table-column prop="val3" align="center" label="预约定金"></el-table-column>
        <el-table-column prop="val4" align="center" label="预约发型师/助理"></el-table-column>
        <el-table-column prop="val5" align="center" label="预约人姓名"></el-table-column>
        <el-table-column prop="val6" align="center" label="预约人手机号"></el-table-column>
        <el-table-column width="138" prop="val7" align="center" label="预约时间"></el-table-column>
        <el-table-column width="138" prop="val8" align="center" label="下单时间"></el-table-column>
        <el-table-column prop="val9" align="center" label="支付方式"></el-table-column>
        <el-table-column align="center" label="操作">
          <template>
            <span>查看详情 </span><span> 隐藏</span>
          </template>
        </el-table-column>
      </el-table>
    </div>
    <div class="home">
      <el-row class="hyinfo">
        <el-row>
          <el-col :span="6">预约姓名：任骏驰</el-col>
          <el-col :span="6">手机号码：13456789876</el-col>
          <el-col :span="6">会员姓名：任骏驰</el-col>
          <el-col :span="6">会员性别：男</el-col>
          <el-col :span="6">预约时间：8月10日 15:30</el-col>
          <el-col :span="6">预约项目：洗剪吹</el-col>
          <el-col :span="6">会员等级：7折会员</el-col>
          <el-col :span="6">预约方式：前台下单</el-col>
        </el-row>
        <el-row>
          <el-col :span="8">
            发型师：<el-select v-model="val1" placeholder="请选择">
              <el-option value="技术总监"></el-option>
              <el-option value="技术总监1"></el-option>
              <el-option value="技术总监2"></el-option>
              <el-option value="技术总监3"></el-option>
              <el-option value="技术总监4"></el-option>
            </el-select>
          </el-col>
          <el-col :span="8">
            助理：<el-select v-model="val2" placeholder="请选择">
              <el-option value="助理"></el-option>
              <el-option value="助理1"></el-option>
              <el-option value="助理2"></el-option>
              <el-option value="助理3"></el-option>
              <el-option value="助理4"></el-option>
            </el-select>
          </el-col>
        </el-row>
      </el-row>
      <el-divider content-position="left">已选择的服务项目</el-divider>
      <el-table class="homeTable" :data="tableData1" border style="width: 910px;" height="360px">
        <el-table-column prop="date" label="分类" align="center"></el-table-column>
        <el-table-column prop="name" label="名称" align="center"></el-table-column>
        <el-table-column prop="address" label="规格" width="150" align="center">
          <template slot-scope="scope">
            <el-select v-model="scope.row.address" placeholder="请选择">
              <el-option value="技术总监"></el-option>
              <el-option value="技术总监1"></el-option>
              <el-option value="技术总监2"></el-option>
              <el-option value="技术总监3"></el-option>
              <el-option value="技术总监4"></el-option>
            </el-select>
          </template>
        </el-table-column>
        <el-table-column prop="danjia" label="单价" align="center"></el-table-column>
        <el-table-column label="数量" align="center">
          <template slot-scope="scope">
            <el-input-number style="width:100%" v-model="scope.row.number" size="small" controls-position="right"
              :min="1" :max="99"></el-input-number>
          </template>
        </el-table-column>
        <el-table-column prop="yhtype" label="优惠类型" align="center"></el-table-column>
        <el-table-column prop="yhnmber" label="优惠" align="center"></el-table-column>
        <el-table-column label="操作" align="center">
          <el-button type="danger" icon="el-icon-delete" title="删除" circle></el-button>
        </el-table-column>
      </el-table>

      <el-divider content-position="left">外卖</el-divider>

      <el-table class="homeTable" :data="tableData2" border style="width: 910px;">
        <el-table-column prop="date" label="商品名称" width="320" align="left"></el-table-column>
        <el-table-column prop="danjia" label="单价" align="center"></el-table-column>
        <el-table-column label="数量">
          <template slot-scope="scope">
            <el-input-number style="width:100%" v-model="scope.row.number" size="small" controls-position="right"
              :min="1" :max="99"></el-input-number>
          </template>
        </el-table-column>
        <el-table-column prop="yhtype" label="优惠类型" align="center"></el-table-column>
        <el-table-column prop="yhnmber" label="优惠" align="center"></el-table-column>
        <el-table-column label="操作" align="center">
          <el-button type="danger" icon="el-icon-delete" title="删除" circle></el-button>
        </el-table-column>
      </el-table>

      <el-row class="width910" :gutter="20">
        <el-col :span="10">
          <el-input v-model="ddje" class="colorF00" readonly>
            <template slot="prepend">订单金额</template>
          </el-input>
        </el-col>
        <el-col :span="10">
          <el-input v-model="ssje" class="colorF00" readonly>
            <template slot="prepend">应收金额</template>
          </el-input>
        </el-col>
        <el-col :span="4">
          <el-button style="width:100%" type="primary">保存</el-button>
        </el-col>
      </el-row>

      <el-input type="textarea" :autosize="{minRows: 2, maxRows: 4}" placeholder="备注信息" v-model="textarea2"></el-input>

      <el-row class="width910" :gutter="20">
        <el-col :span="12">
          <el-input placeholder="请输入付款人手机号" v-model="telnumber">
            <template slot="prepend">指定付款人</template>
            <el-button slot="append" icon="el-icon-search"></el-button>
          </el-input>
        </el-col>
        <el-col :span="12">
          <el-input placeholder="请选择优惠券" v-model="textarea2">
            <template slot="prepend">优惠券</template>
          </el-input>
        </el-col>
      </el-row>

      <el-divider content-position="left">选择支付方式</el-divider>

      <el-row></el-row>

      <el-divider content-position="left">选择支付卡</el-divider>
      <el-row class="eltagbox">
        <el-tag v-for="item in items" :key="item.label" :type="item.type" effect="dark" closable>{{item.label}}</el-tag>
        <el-tag><i class="addPlus el-icon-plus"></i> 添加</el-tag>
      </el-row>
      <el-divider content-position="left">选择支付卡</el-divider>
    </div>
  </div>
</template>


<script>
  //这里可以导入其他文件（比如：组件，工具js，第三方插件js，json文件，图片文件等等）
  //例如：import 《组件名称》 from '《组件路径》';

  export default {
    //import引入的组件需要注入到对象中才能使用
    components: {},
    data() {
      //这里存放数据
      return {
        val1: "技术总监2",
        val2: "助理3",
        tableData: [{
          val1: 'YY20200820034039667155',
          val2: '未选择项目',
          val3: '0',
          val4: '大齐/小茹',
          val5: '曹',
          val6: '15901030562',
          val7: '2020-08-21 11:00',
          val8: '2020-08-20 03:40',
          val9: '无需支付',
        }, {
          val1: 'YY20200820034039667155',
          val2: '未选择项目',
          val3: '0',
          val4: '大齐/小茹',
          val5: '曹',
          val6: '15901030562',
          val7: '2020-08-21 11:00',
          val8: '2020-08-20 03:40',
          val9: '无需支付',
        }, {
          val1: 'YY20200820034039667155',
          val2: '未选择项目',
          val3: '0',
          val4: '大齐/小茹',
          val5: '曹',
          val6: '15901030562',
          val7: '2020-08-21 11:00',
          val8: '2020-08-20 03:40',
          val9: '无需支付',
        }, {
          val1: 'YY20200820034039667155',
          val2: '未选择项目',
          val3: '0',
          val4: '大齐/小茹',
          val5: '曹',
          val6: '15901030562',
          val7: '2020-08-21 11:00',
          val8: '2020-08-20 03:40',
          val9: '无需支付',
        }, {
          val1: 'YY20200820034039667155',
          val2: '未选择项目',
          val3: '0',
          val4: '大齐/小茹',
          val5: '曹',
          val6: '15901030562',
          val7: '2020-08-21 11:00',
          val8: '2020-08-20 03:40',
          val9: '无需支付',
        }, {
          val1: 'YY20200820034039667155',
          val2: '未选择项目',
          val3: '0',
          val4: '大齐/小茹',
          val5: '曹',
          val6: '15901030562',
          val7: '2020-08-21 11:00',
          val8: '2020-08-20 03:40',
          val9: '无需支付',
        }, {
          val1: 'YY20200820034039667155',
          val2: '未选择项目',
          val3: '0',
          val4: '大齐/小茹',
          val5: '曹',
          val6: '15901030562',
          val7: '2020-08-21 11:00',
          val8: '2020-08-20 03:40',
          val9: '无需支付',
        }, {
          val1: 'YY20200820034039667155',
          val2: '未选择项目',
          val3: '0',
          val4: '大齐/小茹',
          val5: '曹',
          val6: '15901030562',
          val7: '2020-08-21 11:00',
          val8: '2020-08-20 03:40',
          val9: '无需支付',
        }, {
          val1: 'YY20200820034039667155',
          val2: '未选择项目',
          val3: '0',
          val4: '大齐/小茹',
          val5: '曹',
          val6: '15901030562',
          val7: '2020-08-21 11:00',
          val8: '2020-08-20 03:40',
          val9: '无需支付',
        }, {
          val1: 'YY20200820034039667155',
          val2: '未选择项目',
          val3: '0',
          val4: '大齐/小茹',
          val5: '曹',
          val6: '15901030562',
          val7: '2020-08-21 11:00',
          val8: '2020-08-20 03:40',
          val9: '无需支付',
        }, {
          val1: 'YY20200820034039667155',
          val2: '未选择项目',
          val3: '0',
          val4: '大齐/小茹',
          val5: '曹',
          val6: '15901030562',
          val7: '2020-08-21 11:00',
          val8: '2020-08-20 03:40',
          val9: '无需支付',
        }, {
          val1: 'YY20200820034039667155',
          val2: '未选择项目',
          val3: '0',
          val4: '大齐/小茹',
          val5: '曹',
          val6: '15901030562',
          val7: '2020-08-21 11:00',
          val8: '2020-08-20 03:40',
          val9: '无需支付',
        }, {
          val1: 'YY20200820034039667155',
          val2: '未选择项目',
          val3: '0',
          val4: '大齐/小茹',
          val5: '曹',
          val6: '15901030562',
          val7: '2020-08-21 11:00',
          val8: '2020-08-20 03:40',
          val9: '无需支付',
        }, {
          val1: 'YY20200820034039667155',
          val2: '未选择项目',
          val3: '0',
          val4: '大齐/小茹',
          val5: '曹',
          val6: '15901030562',
          val7: '2020-08-21 11:00',
          val8: '2020-08-20 03:40',
          val9: '无需支付',
        }, {
          val1: 'YY20200820034039667155',
          val2: '未选择项目',
          val3: '0',
          val4: '大齐/小茹',
          val5: '曹',
          val6: '15901030562',
          val7: '2020-08-21 11:00',
          val8: '2020-08-20 03:40',
          val9: '无需支付',
        }, {
          val1: 'YY20200820034039667155',
          val2: '未选择项目',
          val3: '0',
          val4: '大齐/小茹',
          val5: '曹',
          val6: '15901030562',
          val7: '2020-08-21 11:00',
          val8: '2020-08-20 03:40',
          val9: '无需支付',
        }, {
          val1: 'YY20200820034039667155',
          val2: '未选择项目',
          val3: '0',
          val4: '大齐/小茹',
          val5: '曹',
          val6: '15901030562',
          val7: '2020-08-21 11:00',
          val8: '2020-08-20 03:40',
          val9: '无需支付',
        }, {
          val1: 'YY20200820034039667155',
          val2: '未选择项目',
          val3: '0',
          val4: '大齐/小茹',
          val5: '曹',
          val6: '15901030562',
          val7: '2020-08-21 11:00',
          val8: '2020-08-20 03:40',
          val9: '无需支付',
        }, {
          val1: 'YY20200820034039667155',
          val2: '未选择项目',
          val3: '0',
          val4: '大齐/小茹',
          val5: '曹',
          val6: '15901030562',
          val7: '2020-08-21 11:00',
          val8: '2020-08-20 03:40',
          val9: '无需支付',
        }, {
          val1: 'YY20200820034039667155',
          val2: '未选择项目',
          val3: '0',
          val4: '大齐/小茹',
          val5: '曹',
          val6: '15901030562',
          val7: '2020-08-21 11:00',
          val8: '2020-08-20 03:40',
          val9: '无需支付',
        }],
        items: [{
            type: "danger",
            label: "会员卡"
          },
          {
            type: "",
            label: "支付宝"
          },
          {
            type: "success",
            label: "微信"
          },
          {
            type: "warning",
            label: "现金"
          },
        ],
        textarea2: "",
        telnumber: "13910677914",
        ddje: "5038.00",
        ssje: "4838.00",
        tableData1: [{
            date: "洗剪吹",
            name: "标准剪发",
            address: "技术总监4",
            danjia: 500,
            number: 1,
            yhtype: "打折",
            yhnmber: "9",
          },
          {
            date: "烫发",
            name: "离子烫",
            address: "技术总监",
            danjia: 390,
            number: 1,
            yhtype: "立减",
            yhnmber: "50",
          },
          {
            date: "洗剪吹",
            name: "标准剪发",
            address: "技术总监2",
            danjia: 500,
            number: 1,
            yhtype: "打折",
            yhnmber: "9",
          },
          {
            date: "烫发",
            name: "离子烫",
            address: "技术总监1",
            danjia: 390,
            number: 1,
            yhtype: "立减",
            yhnmber: "50",
          },
          {
            date: "洗剪吹",
            name: "标准剪发",
            address: "技术总监1",
            danjia: 500,
            number: 1,
            yhtype: "打折",
            yhnmber: "9",
          },
          {
            date: "烫发",
            name: "离子烫",
            address: "技术总监2",
            danjia: 390,
            number: 1,
            yhtype: "立减",
            yhnmber: "50",
          },
        ],
        tableData2: [{
            date: "洗剪吹",
            name: "标准剪发",
            address: "技术总监4",
            danjia: 500,
            number: 1,
            yhtype: "打折",
            yhnmber: "9",
          },
          {
            date: "烫发",
            name: "离子烫",
            address: "技术总监",
            danjia: 390,
            number: 1,
            yhtype: "立减",
            yhnmber: "50",
          },
        ],
      };
    },
    //监听属性 类似于data概念
    computed: {},
    //监控data中的数据变化
    watch: {},
    //方法集合
    methods: {},
    //生命周期 - 创建完成（可以访问当前this实例）
    created() {},
    //生命周期 - 挂载完成（可以访问DOM元素）
    mounted() {},
  };
</script>
<style>
  * {
    margin: 0;
    padding: 0;
  }

  .hyinfo {
    text-align: left;
    line-height: 50px;
  }

  .home {
    width: 910px;
    margin-top: 100px;
    margin: 0 auto;
  }

  .width910 {
    margin: 20px auto;
  }

  .txtright {
    text-align: right;
  }

  .colorF00 .el-input__inner {
    font-size: 20px;
    font-weight: bolder;
    color: #f56c6c;
  }

  .el-divider__text {
    font-size: 16px;
    font-weight: bold;
  }

  .eltagbox {
    text-align: left;
  }

  .eltagbox .el-tag {
    margin-right: 15px;
  }

  .eltablebox {
    width: 100%;
  }

  .homeTableA.el-talbe {
    margin: 0 auto;
  }
</style>