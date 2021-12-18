check out page 1 - for checkout website 
color : pink
card bank : visa
<html CODE>
  <head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <link rel="stylesheet" href="./css/style.css">
</head>
<body>
    <div class="wrapper">
        <div class="card">  
          <h2 class="visa">VISA</h2>
          <h3 class="num">n° 4539  7111  0342  0778</h3>
      
            <h4>name</br>Foulen</h4>
            <h4>EXP</br>10/21</h4>
            <h4>CVC</br>014</h4>
      
        </div>
        <div class="main">
          <div class="content">
            <h1>Payment Details</h1>
            <form>
              
           <!--   <label>Name</label>-->
              <input id="name" type="name" value="Foulen">
              
             <!-- <label>Card Number</label>-->
              <input type="text" value="4539 7111 0342 0778">
              
            <!--  <label>Expiration Date</label>-->
              <input type="month" value="2021-10">
              <input type="user" value="014">
              
            </form>
            <div class="payment">
              <h4>Payment Amount :<div class ="amount"> 50$</div></h4> 
              <button>Pay</button>
              </div>
          </div>
        </div>
      </div>
</body>
</html>
<HTML CODE>
  <css code>
    @import url('https://fonts.googleapis.com/css2?family=Comic+Neue&family=Playfair+Display:wght@500&display=swap');
@import url('https://fonts.googleapis.com/css?family=Open+Sans&display=swap');
@import url('https://fonts.googleapis.com/css?family=Montserrat&display=swap');

body{
  background-image: linear-gradient(to right, #eac1ff, #dfc9ff, #d7d0ff, #d1d6ff, #cedbff);
}
.wrapper{
  position: fixed;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  margin-left: auto;
  margin-right: auto;
}
.content h1{
  font-family: 'Playfair Display', serif;
}
.main{
  background-color: white;
  border: 2px solid #6200EA;
 
  width: 450px;
  height: 350px;
  box-shadow: 0px 8px 60px -10px white;
  border-radius: 10px;
  padding:70px;
  padding-top:10px;
}
.content{
  padding-top:10px;
  padding-left:140px;
  font-family: 'Montserrat Medium';
}
/*inpuuuut*/
input[type=name] {
  background-color: white;
  background-image: url('https://image.flaticon.com/icons/svg/2089/2089773.svg');
  background-position:5px 5px;
  background-size:9%;
  background-repeat: no-repeat;
  padding-left: 40px;
}
input[type=text] {

  background-color: white;
  background-image: url('https://image.flaticon.com/icons/svg/633/633611.svg');
  background-position:5px 5px;
  background-size:9%;
  background-repeat: no-repeat;
  padding-left: 40px;
}
input[type=month] {
  width :66%;
  background-color: white;
  background-image: url('https://image.flaticon.com/icons/svg/2693/2693507.svg');
  background-position:6px 5px;
  background-size:14%;
  background-repeat: no-repeat;
  padding-left: 40px;
  padding-bottom:13px;
  font-family: 'Montserrat Medium';
}
input[type=user] {
  width :32.5%;
  background-color: white;
  background-image: url('https://cdn1.iconfinder.com/data/icons/glyph-card-payment/32/credit_card_CVV_CVC_code_number-512.png');
  background-position:5px 5px;
  background-size:31%;
  background-repeat: no-repeat;
  padding-left: 42px;
}

input{
  width:100%;
  padding: 15px 10px;
  margin: 3px 0;
  box-sizing: border-box;
  border: none;
  border-bottom: 2px solid #96a4e7;
}
.amount{
  float:right;
  right:0;
}
button{
  width:100%;
  padding: 10px 20px;
  margin: 3px 0;
  background-color: #96a4e7; 
  border: none;
  color: white;
  padding: 15px 32px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
  cursor:pointer;
}
/*credit card*/
.card{
  background-image: linear-gradient(to bottom, #96a4e7, #a7a6ee, #baa7f3, #cda8f7, #e1a9f9);
  position:fixed;
  right:70%;
  top:25%;
  float:left;
  
  width:300px;
  height:200px;
  box-shadow: 8px 10px 0px 1px #cedbff ;
  border-radius: 10px;
  font-family: 'Montserrat Thin';
  border: 2px solid #6200EA;
}

.visa{
  padding-left:220px;
  font-style: italic;
  text-shadow: #eac1ff 3px 0 1px;
  color:white;
  /*visa font*/
  font-family: "Myriad Pro", Myriad, "Liberation Sans", "Nimbus Sans L", "Helvetica Neue", Helvetica, Arial, sans-serif;
}
.num{
  color:white;
  text-align:center;
  padding-top:20px;
  line-height:0;
}
.card h4{
  color:white;
  float:left;
  width:33%;
  text-align:center;
}

    <css code>
      
      
      <js code>
        new Vue({
    el: "#app",
    data() {
      return {
        currentCardBackground: Math.floor(Math.random()* 25 + 1), // just for fun :D
        cardName: "",
        cardNumber: "",
        cardMonth: "",
        cardYear: "",
        cardCvv: "",
        minCardYear: new Date().getFullYear(),
        amexCardMask: "#### ###### #####",
        otherCardMask: "#### #### #### ####",
        cardNumberTemp: "",
        isCardFlipped: false,
        focusElementStyle: null,
        isInputFocused: false
      };
    },
    mounted() {
      this.cardNumberTemp = this.otherCardMask;
      document.getElementById("cardNumber").focus();
    },
    computed: {
      getCardType () {
        let number = this.cardNumber;
        let re = new RegExp("^4");
        if (number.match(re) != null) return "visa";
  
        re = new RegExp("^(34|37)");
        if (number.match(re) != null) return "amex";
  
        re = new RegExp("^5[1-5]");
        if (number.match(re) != null) return "mastercard";
  
        re = new RegExp("^6011");
        if (number.match(re) != null) return "discover";
        
        re = new RegExp('^9792')
        if (number.match(re) != null) return 'troy'
  
        return "visa"; // default type
      },
          generateCardNumberMask () {
              return this.getCardType === "amex" ? this.amexCardMask : this.otherCardMask;
      },
      minCardMonth () {
        if (this.cardYear === this.minCardYear) return new Date().getMonth() + 1;
        return 1;
      }
    },
    watch: {
      cardYear () {
        if (this.cardMonth < this.minCardMonth) {
          this.cardMonth = "";
        }
      }
    },
    methods: {
      flipCard (status) {
        this.isCardFlipped = status;
      },
      focusInput (e) {
        this.isInputFocused = true;
        let targetRef = e.target.dataset.ref;
        let target = this.$refs[targetRef];
        this.focusElementStyle = {
          width: `${target.offsetWidth}px`,
          height: `${target.offsetHeight}px`,
          transform: `translateX(${target.offsetLeft}px) translateY(${target.offsetTop}px)`
        }
      },
      blurInput() {
        let vm = this;
        setTimeout(() => {
          if (!vm.isInputFocused) {
            vm.focusElementStyle = null;
          }
        }, 300);
        vm.isInputFocused = false;
      }
    }
  });
        <js code>
