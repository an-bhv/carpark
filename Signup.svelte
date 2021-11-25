<script>
    import {Router, navigate} from "svelte-navigator";
    const nav2 = () => {
        navigate("Otp");
    }
    function onSubmit(e) {
    const formData = new FormData(e.target);

    const data = {};
    for (let field of formData) {
      const [key, value] = field;
      data[key] = value;
    }
    console.log(data);
    fetch('.....',{
        method:'POST',
        headers:{
            'Content-type' : 'application/json',
            'Accept' : 'application/json'
        },
        body:JSON.stringify(data)
    }).then(res=>{
        
        res.json()
    }).then(data=>{
        console.log(data);
        nav2();
        
    }).catch(err => {
        console.log(err.message);
    });
    }
    

</script>

<form on:submit|preventDefault={onSubmit}>
<div class = "login">
    <br><br><br><br><br><br>
    <div class = "title">
        <h1>ParkMyCar <i class="fas fa-car-side"></i>
        </h1>
    </div>
    
    <br><br>
    <div class = "format">
        <div class = "box">

            <div>
            First name:&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&ensp;
            <input type = "text" name = "firstname" class = "firstname">
            </div>
            <br>
        
            <div>
            Last name:&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&ensp;
            <input type = "text" name = "lastname" class = "lastname">
            </div>
            <br>
            
            <div>
            Username:&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&ensp;
            <input type = "text" name = "username" class = "username">
            </div>
            <br>
            
            <div>
            Password:&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;
            <input type = "password" name = "password" class = "password">
            </div>
            <br>

            <div>
            Confirm password:&emsp;&emsp;&emsp;&ensp;
            <input type = "password" name = "cpassword" class = "cpassword">
            </div>
            <br>

            <div>
            Residential Address: &emsp;&emsp;&ensp;
            <input type = "text" name = "Address" class = "address">
            </div>
            <br>

            <div>
                Email ID: &emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&nbsp;
                <input type = "text" name = "email" class = "email">
            </div>
            <br>

            <div>
                Mobile number: &nbsp;&emsp;&emsp;&emsp;&emsp;&nbsp;
                <input type = "text" name = "number" class = "number">
            </div>
            <br>

            <div>
                Car Registration Number:
                <input type = "text" name = "crn" class = "crn">
            </div>
            
            <br><br>
            <div class = "submit-button">
            <button class = "submit-button"><b>Sign up</b></button>
            </div>
            <br>

            <pre>Have an account? Click to <a href = "http://localhost:5000/">Login!</a></pre>
        </div>
    </div>
</div>
</form>

<style>
    
    input{
        margin: 5px;
        text-align: center;
    }

    *{
        padding:0%;
        margin: 0;
        box-sizing: border-box;
    }
 
    .login{
        display: flex;
        align-items: center;
        justify-content: space-around;
        height: 100vh;
        flex-direction: column;
    }

    .box{
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
    }

    h1{
        text-align: center;
    }

    .title{
        font-size: 45px;
        color: #333;
    }
    
    .format{
        background-color: #333 !important;
        padding: 40px;
        border-radius: 20px;
        
    }

    button{
        background-color: lawngreen;
        border-color: #333;
        padding: 5px;
    }

    .submit-button{
        width: 206px;
    }

    a{
        color: blueviolet;
    }

</style>