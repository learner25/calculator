<template>
    <div>
       <h2>stamp duty:</h2> <h1>{{comp_stampduty}} ₤</h1>
    </div>
</template>


<script>

export default {
     props:['propertyValue'],
   data(){
       return{
          firstmatrixparam:[150000,250000] ,
         // propertyValue:67000,
          thirdmatrixparam:[.02,.03],

       }
       
   },
   methods:{
      calcFirstMatrix()
            {
            var truthTable1 = [];
                for(let i=0;i<this.firstmatrixparam.length;i++)
                if(parseInt(this.propertyValue)>this.firstmatrixparam[i])
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
        var subtracted_result=Math.abs(parseInt(this.propertyValue)-this.firstmatrixparam[i])
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
             return g;
          }
   }
}
</script>
