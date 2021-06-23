<template>
<div class="mainpage">
<div class="page-container" dir="rtl">
   <el-row type="flex" class="row-bg container-page" style="padding:10px" justify="center">
  <el-col :span="24"><div class="grid-content bg-purple-dark">
    <el-row >
      <el-col :xs="24" :sm="24" :md="24" :lg="12" :xl="12"><div class="grid-content bg-purple-dark" style="width=100%;"></div></el-col>
      <el-col :xs="24" :sm="24" :md="24" :lg="12" :xl="12"><div class="grid-content bg-purple-dark" style="width=100%;">
      <el-row :gutter="15">
        <el-col :xs="24" :sm="12" :md="4" :lg="8" :xl="8">
        <span>من تاريخ</span>
        <div class="grid-content bg-purple-dark">
            <el-date-picker
              v-model="value1"
              type="date"
              placeholder="من  تاريخ"
              style="width:100%">
            </el-date-picker>
        </div>
      </el-col>
      <el-col :xs="24" :sm="12" :md="4" :lg="8" :xl="8">
        <span>من مستوي</span>
        <div class="grid-content bg-purple-dark">
          <el-input
            placeholder="من مستوى"
            v-model="input">
          </el-input>
        </div>
      </el-col>
      <el-col :xs="24" :sm="12" :md="4" :lg="8" :xl="8">
        <span>اسم الفرع</span>
        <div class="grid-content bg-purple-dark">
          <el-input
            placeholder="الفرع الرئيسي"
            v-model="input2">
          </el-input>
        </div>
      </el-col>
      <el-col :xs="24" :sm="12" :md="4" :lg="8" :xl="8"><div class="grid-content bg-purple-dark" style="width=100%;"></div></el-col>
      <el-col :xs="24" :sm="12" :md="4" :lg="8" :xl="8">
        <span>الى تاريخ</span>
        <div class="grid-content bg-purple-dark">
          <el-date-picker
              v-model="value2"
              type="date"
              placeholder="الى  تاريخ"
              style="width:100%">
            </el-date-picker>
        </div>
      </el-col>
      <el-col :xs="24" :sm="12" :md="4" :lg="8" :xl="8">
        <span>مركز التكلفة </span>
        <div class="grid-content bg-purple-dark">
          <el-input
            placeholder="مركز التكلفة"
            v-model="input3">
          </el-input>
        </div>
      </el-col>
      
      </el-row>  
      </div></el-col>
    </el-row>
    <el-row>
          <el-row style="padding-top:30px;">
            <el-col :xs="24" :sm="24" :md="24" :lg="9" :xl="9" style="padding:0px 5px;"><div class="grid-content bg-purple-dark hidden-lg-only">
            <el-button  v-on:click="ChangeNamefirst()" type="info" id="first_button"  class="buttongroup" size="large" >اظهار  الحسابات التي رصيدها صفر</el-button>
            </div></el-col>
          </el-row>
          <el-row >
            
            <el-col :xs="24" :sm="24" :md="24" :lg="4" :xl="4" style="padding:0px 5px;"><div class="grid-content bg-purple-dark"></div>
            <el-button v-on:click="ChangeNamesecond()" type="info" id="second_button" class="buttongroup">تضمين قيمة المخزون</el-button>
            </el-col>
            <el-col :xs="24" :sm="24" :md="24" :lg="5" :xl="5" style="padding:0px 5px;"><div class="grid-content bg-purple-dark"></div>
            <el-button v-on:click="ChangeNamethierd()" type="info" id="thierd_button"  class="buttongroup">تضمين الارصدة الافتتاحيه</el-button>
            </el-col>
            <el-col :xs="24" :sm="24" :md="24" :lg="14" :xl="15"><div class="grid-content bg-purple-dark" style="width=100%;"></div></el-col>
          </el-row>
    </el-row>
    </div></el-col>
</el-row>
<el-row>
  <el-table
    :data="tableData"
    border
    :row-class-name="tableRowClassName"
    :span-method="arraySpanMethod"
    :cell-style="changetotal"
    style="width: 100%; margin-top:50px;"
    :header-cell-style="{ background: '#287B8D' }">
    <el-table-column
      prop="n"
      label="م"
      width="40">
    </el-table-column>
    <el-table-column
      prop="name"
      label="اسم الحساب"
      width="300">
    </el-table-column>
    <el-table-column
      prop="out"
      label="رصيد الدائن">
    </el-table-column>
        <el-table-column
      prop="in"
      label="رصيد المدين">
    </el-table-column>
  </el-table>
</el-row>
</div>
</div>
</template>

<script>
  export default {
    data() {
      return {
        tableData: [{
          n: '1',
          name: '1000-ابراهيم',
          out: 'No. 189, Grove St, Los Angeles',
          in: 'No. 189, Grove St, Los Angeles'
        }, {
          n: '1',
          name: '1000-ابراهيم',
          out: 'No. 189, Grove St, Los Angeles',
          in: 'No. 189, Grove St, Los Angeles'
        }, {
          n: '1',
          name: '1000-ابراهيم',
          out: 'No. 189, Grove St, Los Angeles',
          in: 'No. 189, Grove St, Los Angeles'
        }, {
          n: 'الاجمالي',
          name: '1000-ابراهيم',
          out: 'No. 189, Grove St, Los Angeles',
          in: 'No. 189, Grove St, Los Angeles'
        }]
      }
      
    },
    methods: {
      arraySpanMethod({ row, column, rowIndex, columnIndex }) {
        if (rowIndex  === 3) {
          if (columnIndex === 0) {
            return [1, 2];
          } else if (columnIndex === 1) {
            return [0, 0];
          }
        }
      },

      objectSpanMethod({ row, column, rowIndex, columnIndex }) {
        if (columnIndex === 0) {
          if (rowIndex % 2 === 0) {
            return {
              rowspan: 2,
              colspan: 1
            };
          } else {
            return {
              rowspan: 0,
              colspan: 0
            };
          }
        }
      },
       tableRowClassName({row, rowIndex ,columnIndex}) {
        if (rowIndex %2 === 0) {
          return 'warning-row';
        } 
        else
        return '';
      },
      changetotal({rowIndex ,columnIndex})
      {
         if (columnIndex  === 0 && rowIndex === 3)
        {
          console.log(rowIndex,columnIndex);
          return {background:"#72D0D0",
          color:"white",
          };
        }
      },
     ChangeNamefirst()
  {
    var elem = document.getElementById("first_button");
    if (elem.innerHTML =="اظهار  الحسابات التي رصيدها صفر")
    {
       elem.innerHTML  = "عدم اظهار  الحسابات التي رصيدها صفر";
       elem.style.background="red";
    }
    else {
      elem.innerHTML  = "اظهار  الحسابات التي رصيدها صفر";
      elem.style.background="gray";
      }
  },
  ChangeNamesecond()
  {
    var elem = document.getElementById("second_button");
    if (elem.innerHTML =="تضمين قيمة المخزون")
    {
       elem.innerHTML  = "عدم تضمين قيمة المخزون";
       elem.style.background="red";
    }
    else {
      elem.innerHTML  = "تضمين قيمة المخزون";
      elem.style.background="gray";
      }
  },
  ChangeNamethierd()
  {
    var elem = document.getElementById("thierd_button");
    if (elem.innerHTML =="تضمين الارصدة الافتتاحيه")
    {
       elem.innerHTML  = "عدم تضمين الارصدة الافتتاحيه";
       elem.style.background="red";
    }
    else {
      elem.innerHTML  = "تضمين الارصدة الافتتاحيه";
      elem.style.background="gray";
      }
  },
    }
    
  }
  
</script>