# online-Placement
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>CampusHire - Online Placement Management System</title>

<style>
*{
    margin:0;
    padding:0;
    box-sizing:border-box;
    font-family:Arial, sans-serif;
}

body{
    background:#f4f7fb;
    color:#222;
}

/* LOGIN */
.login-page{
    min-height:100vh;
    display:flex;
    justify-content:center;
    align-items:center;
    background:linear-gradient(135deg,#164e8a,#4f8edb);
}

.login-box{
    width:380px;
    background:white;
    padding:35px;
    border-radius:15px;
    box-shadow:0 10px 30px rgba(0,0,0,.2);
}

.login-box h1{
    text-align:center;
    color:#164e8a;
    margin-bottom:8px;
}

.login-box p{
    text-align:center;
    color:#777;
    margin-bottom:25px;
}

.login-box input,
.login-box select{
    width:100%;
    padding:13px;
    margin:9px 0;
    border:1px solid #ccc;
    border-radius:7px;
}

.login-btn{
    width:100%;
    padding:13px;
    margin-top:12px;
    border:none;
    border-radius:7px;
    background:#164e8a;
    color:white;
    font-size:16px;
    cursor:pointer;
}

.login-btn:hover{
    background:#0d3865;
}

.demo{
    margin-top:18px;
    padding:12px;
    background:#eef5ff;
    border-radius:8px;
    font-size:13px;
}

/* DASHBOARD */
.dashboard{
    display:none;
    min-height:100vh;
}

.navbar{
    height:65px;
    background:#164e8a;
    color:white;
    display:flex;
    align-items:center;
    justify-content:space-between;
    padding:0 30px;
}

.navbar h2{
    font-size:22px;
}

.logout{
    background:#e63946;
    color:white;
    border:none;
    padding:9px 18px;
    border-radius:6px;
    cursor:pointer;
}

.container{
    padding:30px;
}

.welcome{
    margin-bottom:25px;
}

.cards{
    display:grid;
    grid-template-columns:repeat(4,1fr);
    gap:20px;
    margin-bottom:30px;
}

.card{
    background:white;
    padding:25px;
    border-radius:12px;
    box-shadow:0 3px 12px rgba(0,0,0,.08);
}

.card h3{
    color:#164e8a;
    margin-bottom:10px;
}

.card .number{
    font-size:28px;
    font-weight:bold;
}

.section{
    background:white;
    padding:25px;
    border-radius:12px;
    margin-bottom:25px;
    box-shadow:0 3px 12px rgba(0,0,0,.07);
}

.section h2{
    color:#164e8a;
    margin-bottom:18px;
}

table{
    width:100%;
    border-collapse:collapse;
}

th,td{
    padding:13px;
    border-bottom:1px solid #ddd;
    text-align:left;
}

th{
    background:#eef5ff;
    color:#164e8a;
}

.apply{
    background:#164e8a;
    color:white;
    border:none;
    padding:7px 14px;
    border-radius:5px;
    cursor:pointer;
}

.status{
    padding:5px 10px;
    border-radius:15px;
    font-size:12px;
    background:#dff5e1;
    color:#188038;
}

@media(max-width:800px){
    .cards{
        grid-template-columns:repeat(2,1fr);
    }
}

@media(max-width:500px){
    .cards{
        grid-template-columns:1fr;
    }

    .container{
        padding:15px;
    }

    .login-box{
        width:90%;
    }
}
</style>
</head>

<body>

<!-- LOGIN PAGE -->
<div class="login-page" id="loginPage">

    <div class="login-box">

        <h1>CampusHire</h1>
        <p>Online Placement Management System</p>

        <select id="role">
            <option value="student">Student Login</option>
            <option value="admin">Admin / TPO Login</option>
        </select>

        <input type="email" id="email"
        placeholder="Enter Email">

        <input type="password" id="password"
        placeholder="Enter Password">

        <button class="login-btn" onclick="login()">
            Login
        </button>

        <div class="demo">
            <b>Demo Student</b><br>
            Email: student@campushire.com<br>
            Password: 123456
            <br><br>

            <b>Demo Admin</b><br>
            Email: admin@campushire.com<br>
            Password: admin123
        </div>

    </div>
</div>


<!-- STUDENT DASHBOARD -->
<div class="dashboard" id="studentDashboard">

    <div class="navbar">
        <h2>CampusHire</h2>
        <button class="logout" onclick="logout()">Logout</button>
    </div>

    <div class="container">

        <div class="welcome">
            <h1>Welcome, Student 👋</h1>
            <p>Manage your placement activities from here.</p>
        </div>

        <div class="cards">

            <div class="card">
                <h3>Eligible Drives</h3>
                <div class="number">08</div>
            </div>

            <div class="card">
                <h3>Applications</h3>
                <div class="number">05</div>
            </div>

            <div class="card">
                <h3>Shortlisted</h3>
                <div class="number">02</div>
            </div>

            <div class="card">
                <h3>Placement Status</h3>
                <div class="number">Active</div>
            </div>

        </div>

        <div class="section">

            <h2>Available Placement Drives</h2>

            <table>

                <tr>
                    <th>Company</th>
                    <th>Job Role</th>
                    <th>Package</th>
                    <th>Eligibility</th>
                    <th>Action</th>
                </tr>

                <tr>
                    <td>TCS</td>
                    <td>Software Developer</td>
                    <td>7 LPA</td>
                    <td>MCA / BCA</td>
                    <td>
                        <button class="apply"
                        onclick="applyJob('TCS')">
                        Apply
                        </button>
                    </td>
                </tr>

                <tr>
                    <td>Capgemini</td>
                    <td>Analyst</td>
                    <td>6.5 LPA</td>
                    <td>MCA / BCA</td>
                    <td>
                        <button class="apply"
                        onclick="applyJob('Capgemini')">
                        Apply
                        </button>
                    </td>
                </tr>

                <tr>
                    <td>Infosys</td>
                    <td>System Engineer</td>
                    <td>6 LPA</td>
                    <td>MCA / BCA</td>
                    <td>
                        <button class="apply"
                        onclick="applyJob('Infosys')">
                        Apply
                        </button>
                    </td>
                </tr>

                <tr>
                    <td>Accenture</td>
                    <td>Associate Software Engineer</td>
                    <td>5.5 LPA</td>
                    <td>MCA / BCA</td>
                    <td>
                        <button class="apply"
                        onclick="applyJob('Accenture')">
                        Apply
                        </button>
                    </td>
                </tr>

            </table>

        </div>

        <div class="section">

            <h2>My Applications</h2>

            <table>

                <tr>
                    <th>Company</th>
                    <th>Role</th>
                    <th>Status</th>
                </tr>

                <tr>
                    <td>TCS</td>
                    <td>Software Developer</td>
                    <td>
                        <span class="status">
                        Applied
                        </span>
                    </td>
                </tr>

                <tr>
                    <td>Capgemini</td>
                    <td>Analyst</td>
                    <td>
                        <span class="status">
                        Shortlisted
                        </span>
                    </td>
                </tr>

            </table>

        </div>

    </div>
</div>


<!-- ADMIN DASHBOARD -->
<div class="dashboard" id="adminDashboard">

    <div class="navbar">
        <h2>CampusHire - Admin Panel</h2>
        <button class="logout" onclick="logout()">Logout</button>
    </div>

    <div class="container">

        <div class="welcome">
            <h1>Welcome, Admin / TPO 👋</h1>
            <p>Manage college placement activities.</p>
        </div>

        <div class="cards">

            <div class="card">
                <h3>Total Students</h3>
                <div class="number">850</div>
            </div>

            <div class="card">
                <h3>Companies</h3>
                <div class="number">32</div>
            </div>

            <div class="card">
                <h3>Applications</h3>
                <div class="number">1250</div>
            </div>

            <div class="card">
                <h3>Placed Students</h3>
                <div class="number">275</div>
            </div>

        </div>

        <div class="section">

            <h2>Placement Drives</h2>

            <table>

                <tr>
                    <th>Company</th>
                    <th>Role</th>
                    <th>Package</th>
                    <th>Applications</th>
                    <th>Status</th>
                </tr>

                <tr>
                    <td>TCS</td>
                    <td>Software Developer</td>
                    <td>7 LPA</td>
                    <td>250</td>
                    <td>Active</td>
                </tr>

                <tr>
                    <td>Capgemini</td>
                    <td>Analyst</td>
                    <td>6.5 LPA</td>
                    <td>190</td>
                    <td>Active</td>
                </tr>

                <tr>
                    <td>Infosys</td>
                    <td>System Engineer</td>
                    <td>6 LPA</td>
                    <td>160</td>
                    <td>Completed</td>
                </tr>

            </table>

        </div>

        <div class="section">

            <h2>Admin Functions</h2>

            <button class="apply"
            onclick="alert('Add Company module')">
            Add Company
            </button>

            <button class="apply"
            onclick="alert('Post Drive module')">
            Post Placement Drive
            </button>

            <button class="apply"
            onclick="alert('Student Management module')">
            Manage Students
            </button>

            <button class="apply"
            onclick="alert('Application Management module')">
            Manage Applications
            </button>

        </div>

    </div>
</div>


<script>

function login(){

    let role =
    document.getElementById("role").value;

    let email =
    document.getElementById("email").value;

    let password =
    document.getElementById("password").value;


    if(role === "student" &&
       email === "student@campushire.com" &&
       password === "123456"){

        document.getElementById("loginPage").style.display="none";

        document.getElementById("studentDashboard").style.display="block";
    }

    else if(role === "admin" &&
            email === "admin@campushire.com" &&
            password === "admin123"){

        document.getElementById("loginPage").style.display="none";

        document.getElementById("adminDashboard").style.display="block";
    }

    else{

        alert("Invalid Email or Password");

    }

}


function logout(){

    document.getElementById("studentDashboard").style.display="none";

    document.getElementById("adminDashboard").style.display="none";

    document.getElementById("loginPage").style.display="flex";

    document.getElementById("email").value="";
    document.getElementById("password").value="";
}


function applyJob(company){

    alert(
        "Application submitted successfully for "
        + company
    );

}

</script>

</body>
</html>
