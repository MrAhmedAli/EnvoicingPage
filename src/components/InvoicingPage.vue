<template>

<div class="container-fluid"> 
<div class="left_elements">

  <label class="form-label">full name <label style="color: #CD1717;">*</label></label>
  <input type="text" class="form-control"  placeholder="enter your full name">

  <label class="form-label">company name <label style="color: var(--a-4-b-4-cb, #A4B4CB);">(if Any)</label></label>
  <input type="text" class="form-control"  placeholder="enter company name">

  <label  class="form-label">type of proof <label style="color: #CD1717;">*</label></label>
  <DropdownOptions :options="options[0]" />

    <div class="">
      <label class="form-label">proof number <label style="color: #CD1717;">*</label></label>
      <input type="text" class="form-control" placeholder="enter proof number">
    </div>
    <div class="">
      <label class="form-label">VAT number</label>
      <input type="text" class="form-control"  placeholder="enter Vat number">
    </div>

     <p class="TitleNote_text">importent notes</p>
     <div v-for="(note,index) in notes" :key="index"  class="form-check">
        <p class="notes_text"><svg xmlns="http://www.w3.org/2000/svg" width="15" height="15" viewBox="0 0 15 15" fill="none">
        <circle cx="7.5" cy="7.5" r="7.5" fill="#3AC2CB"/></svg> {{note.note}}</p>
     </div>

</div>

<div class="middle_line"></div>

   <div class="right_elements">

        <label  class="form-label">country <label style="color: #CD1717;">*</label></label>
        <DropdownOptions :options="options[1]" />
      
        <label  class="form-label">Province <label style="color: #CD1717;">*</label></label>
        <DropdownOptions :options="options[2]" />

        <label  class="form-label">City <label style="color: #CD1717;">*</label></label>
        <DropdownOptions :options="options[3]" />

       <label  class="form-label">area <label style="color: #CD1717;">*</label></label>
       <DropdownOptions :options="options[4]" />

       <label class="form-label">street name <label style="color: #CD1717;">*</label></label>
       <input type="text" class="form-control"   placeholder="">

       <label class="form-label">building number  <label style="color: #CD1717;">*</label></label>
       <input type="text" class="form-control"  placeholder="if you don’t know keep it 00000">

       <label class="form-label">postal code <label style="color: #CD1717;">*</label></label>
       <input type="text" class="form-control"  placeholder="if you don’t know keep it 00000">
    
  </div>
</div>

</template>

<script>
import DropdownOptions from './DropdownOptions.vue';

export default { 
  components: {
    DropdownOptions
  },
  data(){
   return{
    notes:[
    {note:'Taxpayers or non-taxes must enter data'},
    {note:'Data is only effective for those who pay taxes'},
    {note:'You can later integrate with your accounting system'}
          ],  
    options:[
    {   option1:'Commercial Registration No',
        option2:'Momra license no',
        option3:'MLSD License No',
        option4:'Sagia License No',
        option5:'Another license no',},
    {   option1:'Saudi Arabia',
        option2:'China',
        option3:'Syria',
    },
    { option1:'Eastern Province',
        option2:'Riyadh',
        option3:'Makkah',
    },  
    { option1:'Alhasa',
        option2:'Jeddah',
        option3:'Taif',
    }, 
    { option1:'Alhasa',
        option2:'Jeddah',
        option3:'Taif',
    }, 
        ]};
       },};
</script>

<style scoped>

@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@400;500;700&display=swap");

.container-fluid{
   width: auto;
   display: flex;
   line-height: normal;
   font-style: normal;
   font-family: Poppins;
   text-transform: capitalize;
   font-weight: 500;
   margin-left: 190px;}

.form-label{
    color: var(--fafafa, #FAFAFA);
    font-size: 16px;
    margin-top: 10px;}
    
.form-select,.form-control{
    background-color: var(--36415-c, #36415C);
    color: var(--fafafa, #FAFAFA);
    width: 500px;
    height: 60px;
    border-radius: 10px;
    border: none;}

::placeholder{
    color: var(--a-4-b-4-cb, #A4B4CB);
    text-transform: capitalize;}

.TitleNote_text{
    color: #FFF;
    font-size: 20px;
    margin-top: 86px;}

.notes_text{
    color: var(--a-4-b-4-cb, #A4B4CB);
    font-size: 16px;
    margin-left: -28px;}

.middle_line {
    border: 1px solid var(--a-4-b-4-cb, #A4B4CB);;
    height: 610px;
    opacity: 0.2;
    width: 1px;
    margin: 10px 0px 0px 270px;}

.right_elements{margin-left: 100px;}

@media (max-width: 1400px) { 
  .container-fluid{      
       width: 100%;
       display:block;}
  .middle_line {display: none;}   
  .right_elements{margin:100px 0px 0px 0px;}} 
</style>
