
<template>
    <!--<div>
      <h2>multi stamp duty:</h2> <h1>{{comp_stampduty}} ₤</h1>  
    </div>-->
</template>


<script>
window.MultiStampDuty =0;
export default {
     props:['propertyValue'],
   data(){
       return{
          firstmatrixparam:[40000,125000,250000,925000,1500000] ,
          //propertyValue:300000,
          thirdmatrixparam:[.03,.02,.03,.05,.02],

       }
       
   },
   methods:{
      calcFirstMatrix()
            {
            var truthTable1 = [];
                for(let i=0;i<this.firstmatrixparam.length;i++)
                if(this.propertyValue>this.firstmatrixparam[i])
                {
                   truthTable1.push (1);
                 }
                else truthTable1.push(0);
                
                return truthTable1;
            },

    calcSecondMatrix()
        {
        var truthTable2 = [];
        for(let i=0;i<this.firstmatrixparam.length;i++){
        var subtracted_result=Math.abs(this.propertyValue-this.firstmatrixparam[i])
              {
                truthTable2.push(subtracted_result);
                
              }
            
            }
            
            return truthTable2;
        },
    sumproduct (c1,c2,c3)
        {
 
  let products = []
  let sumproduct = 0
  if(c1.length!=c2.length || c1.length!=c3.length||c2.length!=c3.length) 
    return 0;
  for(var i=0;i<c2.length;i++){
     console.log('vars'+i,c1[i]*c2[i]*c3[i])
      products.push(c1[i]*c2[i]*c3[i]);
      }
       for(var i=0;i<products.length;i++){
         sumproduct+=products[i]
       }
         
        return sumproduct
        }
   },
   computed:{
          firstmatrix(){
              var d = this.calcFirstMatrix()
              return d;
          },
          secondmatrix(){
             var d = this.calcSecondMatrix()
              return d;
          },
          comp_stampduty(){
              
             var g = this.sumproduct(this.firstmatrix,this.secondmatrix,this.thirdmatrixparam)
             window.MultiStampDuty= g+1200*1;
             return  window.MultiStampDuty;
          }
   },
   watch:{
       comp_stampduty:function(newval)
       {
          // alert(newval+'changed new stampduty')
            this.$emit('multiple_stamp_duty_changed',newval)
       }
   }
}
</script>
