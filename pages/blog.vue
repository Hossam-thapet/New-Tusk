<template>
   
   <div class="container shadow-lg mt-5 p-0 " st dir="rtl">
       <div class="row p-3 mt-5">
            <div class="col-sm-6 pb-5">
                <div class="row">
                    <div class="col-md-4">
                        <div class="input-title" style="text-align: right;">
                            <span class="font-weight-bold">اسم الفرع</span>
                            <input type="text" class="form-control mt-2" placeholder="الفرع الرئيسي"> 
                        </div>
                    </div>
                    <div class="col-md-4 ">
                        <div class="input-title" style="text-align: right;">
                            <span class="font-weight-bold">المستوي</span>
                            <input type="text" class="form-control mt-2" placeholder="المستوي"> 
                        </div>
                    </div>
                    <div class="col-md-4 ">
                        <div class="input-title" style="text-align: right;">
                            <span class="font-weight-bold">التاريخ من</span>
                            <input type="date" class="form-control mt-2" placeholder="الفرع الرئيسي"> 
                        </div>
                    </div>
                    <div class="col-md-4 ">
                        <div class="input-title" style="text-align: right;">
                            <span class="font-weight-bold">مركز التكلفة</span>
                            <input type="text" class="form-control mt-2" placeholder="مركز التكلفه"> 
                        </div>
                    </div>
                    <div class="col-md-4 ">
                        <div class="input-title" style="text-align: right;">
                            <span class="font-weight-bold">التاريخ الى</span>
                            <input type="date" class="form-control mt-2" placeholder="التاريخ الى"> 
                        </div>
                    </div>
                </div>
            </div>
            <div class="col-lg-2"></div>
                <div class="col-lg-4" style="padding-top:100px;">
                    <div class="row">
                        <div class="col-md-12 mb-2">
                            <button type="button" class="btn btn-secondary w-100 second">اظهار الحسابات التي رصيدها صفر</button>
                        </div>
                        <div class="col-md-6 mb-2">
                            <button type="button" class="btn btn-secondary second w-100 ">تضمين قيمه المخزون</button>
                        </div>
                        <div class="col-md-6 mb-2">
                            <button type="button" class="btn btn-secondary second w-100 pb-1">تضمين الارصده الافتتاحيه</button>
                        </div>
                    </div>
                </div>
            </div>
            <div class="continer-fluid">
            <table class="w-100">
           <tr>
                <th style="width:4%;">م</th>
                <th style="width:32%;">اسم الحساب</th>
                <th style="width:32%;">رصيد الدائن </th>
                <th style="width:32%;">رصيد المدان</th>
           </tr>
           <tr>
                <td>1</td>
                <td>1000-ابراهيم</td>
                <td>1</td>
                <td>1</td>
           </tr>
             <tr>
                <td>2</td>
                <td>2000-السيد</td>
                <td>1</td>
                <td>1</td>
           </tr>
             <tr>
                <td>3</td>
                <td>3000-سعيد</td>
                <td>1</td>
                <td>1</td>
           </tr>
           <tr class="last"  colspan="2">
               <td colspan="2" class="last" style="background-color:#72D0D0; color:white; border-bottom-right-radius: 10px;">الاجمالي</td>
               <td colspan="1" class="last">1</td>
               <td colspan="1" class="last left">1</td>
           </tr>
       </table>
   </div>
</div>
</template>