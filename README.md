<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>SHAMMAH MISSION SCHOOL PORTAL</title>

<style>
*{box-sizing:border-box}
body{
 margin:0;
 font-family:Arial,Helvetica,sans-serif;
 background:#f1f5f9;
 color:#172033;
}
button,input,select,textarea{font:inherit}
button{
 border:0;
 border-radius:8px;
 padding:10px 14px;
 cursor:pointer;
 background:#164e63;
 color:white;
}
button:hover{opacity:.9}
input,select,textarea{
 width:100%;
 padding:10px;
 border:1px solid #cbd5e1;
 border-radius:7px;
 background:white;
}
.hidden{display:none!important}

.login{
 min-height:100vh;
 display:flex;
 align-items:center;
 justify-content:center;
 padding:20px;
 background:linear-gradient(135deg,#164e63,#0f766e);
}
.login-card{
 width:100%;
 max-width:430px;
 background:white;
 padding:30px;
 border-radius:18px;
 box-shadow:0 15px 40px rgba(0,0,0,.25);
 text-align:center;
}
.logo{
 width:100px;
 height:100px;
 border-radius:50%;
 object-fit:contain;
 border:2px solid #ddd;
 margin-bottom:12px;
}
.login-card h1{font-size:23px;margin:5px 0}
.login-card p{color:#64748b}
.form-group{text-align:left;margin:15px 0}
.login-btn{width:100%;font-size:16px}
.error{color:#dc2626;margin-top:10px}

.app{min-height:100vh}
.topbar{
 background:#164e63;
 color:white;
 padding:13px 18px;
 display:flex;
 justify-content:space-between;
 align-items:center;
 gap:10px;
 position:sticky;
 top:0;
 z-index:20;
}
.brand{font-weight:bold}
.topbar small{display:block;opacity:.85}
.logout{background:#b91c1c}

.layout{display:flex;min-height:calc(100vh - 65px)}
.sidebar{
 width:240px;
 background:#0f172a;
 color:white;
 padding:15px;
}
.nav-btn{
 width:100%;
 text-align:left;
 background:transparent;
 margin:3px 0;
}
.nav-btn.active,.nav-btn:hover{background:#164e63}

.main{
 flex:1;
 padding:20px;
 min-width:0;
}
.page-title{
 display:flex;
 justify-content:space-between;
 align-items:center;
 gap:10px;
 flex-wrap:wrap;
 margin-bottom:18px;
}
.page-title h2{margin:0}

.cards{
 display:grid;
 grid-template-columns:repeat(auto-fit,minmax(180px,1fr));
 gap:15px;
}
.card{
 background:white;
 padding:18px;
 border-radius:12px;
 box-shadow:0 2px 8px rgba(0,0,0,.07);
}
.card h3{margin:0 0 8px}
.number{font-size:30px;font-weight:bold;color:#164e63}

.panel{
 background:white;
 padding:18px;
 border-radius:12px;
 margin-bottom:18px;
 box-shadow:0 2px 8px rgba(0,0,0,.06);
}
.panel h3{margin-top:0}

.grid{
 display:grid;
 grid-template-columns:repeat(auto-fit,minmax(180px,1fr));
 gap:12px;
}
.actions{
 display:flex;
 flex-wrap:wrap;
 gap:8px;
 margin-top:12px;
}
.danger{background:#b91c1c}
.success{background:#15803d}
.warning{background:#b45309}
.secondary{background:#475569}

table{
 width:100%;
 border-collapse:collapse;
 background:white;
}
th,td{
 padding:9px;
 border:1px solid #e2e8f0;
 text-align:left;
}
th{background:#e2e8f0}
.table-wrap{overflow:auto}

.badge{
 display:inline-block;
 padding:4px 8px;
 border-radius:20px;
 background:#e2e8f0;
 font-size:12px;
}
.grade-EE{background:#bbf7d0;color:#166534}
.grade-ME{background:#bfdbfe;color:#1e3a8a}
.grade-AE{background:#fde68a;color:#854d0e}
.grade-BE{background:#fecaca;color:#991b1b}

.report{
 background:white;
 max-width:850px;
 margin:auto;
 padding:30px;
 border:1px solid #cbd5e1;
}
.report-header{text-align:center;border-bottom:2px solid #164e63;padding-bottom:15px}
.report-logo{width:80px;height:80px;object-fit:contain}
.report-title{font-size:22px;font-weight:bold}
.report-subtitle{color:#475569}
.report-info{
 display:grid;
 grid-template-columns:1fr 1fr;
 gap:8px;
 margin:15px 0;
}
.remark{
 border:1px solid #cbd5e1;
 padding:10px;
 min-height:50px;
 margin-top:10px;
}

.modal{
 position:fixed;
 inset:0;
 background:rgba(0,0,0,.55);
 display:flex;
 align-items:center;
 justify-content:center;
 padding:15px;
 z-index:50;
}
.modal-box{
 width:100%;
 max-width:600px;
 max-height:90vh;
 overflow:auto;
 background:white;
 border-radius:12px;
 padding:20px;
}

.notice{
 padding:12px;
 border-radius:8px;
 background:#ecfeff;
 border:1px solid #a5f3fc;
 margin-bottom:12px;
}

@media(max-width:750px){
 .layout{display:block}
 .sidebar{
  width:100%;
  display:flex;
  overflow-x:auto;
  gap:5px;
 }
 .nav-btn{min-width:max-content;width:auto}
 .main{padding:12px}
 .topbar{position:relative}
 .report-info{grid-template-columns:1fr}
}

@media print{
 .no-print,.sidebar,.topbar{display:none!important}
 .main{padding:0}
 .report{border:0;box-shadow:none;max-width:none}
}
</style>
</head>

<body>

<!-- LOGIN -->
<div id="loginPage" class="login">
 <div class="login-card">
  <img id="loginLogo" class="logo" src="" alt="School Logo">
  <h1>SHAMMAH MISSION SCHOOL</h1>
  <p>Results Management Portal</p>

  <div class="form-group">
   <label>Username</label>
   <input id="loginUsername" placeholder="Enter username">
  </div>

  <div class="form-group">
   <label>Password</label>
   <input id="loginPassword" type="password" placeholder="Enter password">
  </div>

  <button class="login-btn" onclick="login()">Login</button>
  <div id="loginError" class="error"></div>
 </div>
</div>

<!-- APPLICATION -->
<div id="app" class="app hidden">

 <div class="topbar">
  <div>
   <div class="brand">SHAMMAH MISSION SCHOOL PORTAL</div>
   <small id="currentUser"></small>
  </div>
  <button class="logout" onclick="logout()">Logout</button>
 </div>

 <div class="layout">

  <aside class="sidebar">
   <button class="nav-btn active" onclick="showPage('dashboard',this)">🏠 Dashboard</button>
   <button class="nav-btn" onclick="showPage('students',this)">👨‍🎓 Students</button>
   <button class="nav-btn" onclick="showPage('teachers',this)">👨‍🏫 Teachers</button>
   <button class="nav-btn" onclick="showPage('subjects',this)">📚 Subjects</button>
   <button class="nav-btn" onclick="showPage('results',this)">📝 Results</button>
   <button class="nav-btn" onclick="showPage('analysis',this)">📊 Analysis</button>
   <button class="nav-btn" onclick="showPage('reports',this)">🖨️ Report Cards</button>
   <button class="nav-btn" onclick="showPage('history',this)">📅 History</button>
   <button class="nav-btn" onclick="showPage('settings',this)">⚙️ School Settings</button>
  </aside>

  <main class="main">

   <!-- DASHBOARD -->
   <section id="page-dashboard" class="page">
    <div class="page-title">
     <h2>Director Dashboard</h2>
    </div>

    <div class="cards">
     <div class="card">
      <h3>Students</h3>
      <div id="dashStudents" class="number">0</div>
     </div>
     <div class="card">
      <h3>Teachers</h3>
      <div id="dashTeachers" class="number">0</div>
     </div>
     <div class="card">
      <h3>Subjects</h3>
      <div id="dashSubjects" class="number">0</div>
     </div>
     <div class="card">
      <h3>Results</h3>
      <div id="dashResults" class="number">0</div>
     </div>
    </div>

    <div class="panel" style="margin-top:18px">
     <h3>Quick Actions</h3>
     <div class="actions">
      <button onclick="showPage('students')">Add Student</button>
      <button onclick="showPage('results')">Enter Results</button>
      <button onclick="showPage('reports')">Print Report Cards</button>
      <button onclick="showPage('analysis')">View Analysis</button>
     </div>
    </div>

    <div class="panel">
     <h3>Current Academic Period</h3>
     <div class="grid">
      <div>
       <label>Year</label>
       <input id="globalYear" type="number" onchange="saveAcademic()">
      </div>
      <div>
       <label>Term</label>
       <select id="globalTerm" onchange="saveAcademic()">
        <option>Term 1</option>
        <option>Term 2</option>
        <option>Term 3</option>
       </select>
      </div>
     </div>
    </div>
   </section>

   <!-- STUDENTS -->
   <section id="page-students" class="page hidden">
    <div class="page-title">
     <h2>Student Management</h2>
     <button onclick="openStudentModal()">+ Add Student</button>
    </div>

    <div class="panel">
     <div class="grid">
      <input id="studentSearch" placeholder="Search name/admission..." oninput="renderStudents()">
      <select id="studentFilterGrade" onchange="renderStudents()">
       <option value="">All Grades</option>
       <option>Grade 7</option>
       <option>Grade 8</option>
       <option>Grade 9</option>
      </select>
     </div>
    </div>

    <div class="panel table-wrap">
     <table>
      <thead>
       <tr>
        <th>#</th>
        <th>Admission</th>
        <th>Name</th>
        <th>Gender</th>
        <th>Grade</th>
        <th>Parent Phone</th>
        <th>Actions</th>
       </tr>
      </thead>
      <tbody id="studentsTable"></tbody>
     </table>
    </div>
   </section>

   <!-- TEACHERS -->
   <section id="page-teachers" class="page hidden">
    <div class="page-title">
     <h2>Teachers & Allocations</h2>
     <button onclick="openTeacherModal()">+ Add Teacher</button>
    </div>

    <div class="panel table-wrap">
     <table>
      <thead>
       <tr>
        <th>Name</th>
        <th>Username</th>
        <th>Phone</th>
        <th>Allocations</th>
        <th>Actions</th>
       </tr>
      </thead>
      <tbody id="teachersTable"></tbody>
     </table>
    </div>
   </section>

   <!-- SUBJECTS -->
   <section id="page-subjects" class="page hidden">
    <div class="page-title">
     <h2>Subjects & Classes</h2>
     <button onclick="openSubjectModal()">+ Add Subject</button>
    </div>

    <div class="panel table-wrap">
     <table>
      <thead>
       <tr>
        <th>Subject</th>
        <th>Code</th>
        <th>Grades</th>
        <th>Actions</th>
       </tr>
      </thead>
      <tbody id="subjectsTable"></tbody>
     </table>
    </div>
   </section>

   <!-- RESULTS -->
   <section id="page-results" class="page hidden">
    <div class="page-title">
     <h2>Results Management</h2>
    </div>

    <div class="panel">
     <div class="grid">
      <div>
       <label>Grade</label>
       <select id="resultGrade" onchange="loadResultStudents()">
        <option>Grade 7</option>
        <option>Grade 8</option>
        <option>Grade 9</option>
       </select>
      </div>
      <div>
       <label>Subject</label>
       <select id="resultSubject"></select>
      </div>
      <div>
       <label>Year</label>
       <input id="resultYear" type="number">
      </div>
      <div>
       <label>Term</label>
       <select id="resultTerm">
        <option>Term 1</option>
        <option>Term 2</option>
        <option>Term 3</option>
       </select>
      </div>
     </div>

     <div class="actions">
      <button onclick="loadResultStudents()">Load Students</button>
      <button class="success" onclick="saveResults()">Save Results</button>
      <button class="warning" onclick="publishResults()">Publish Results</button>
     </div>
    </div>

    <div class="panel table-wrap">
     <table>
      <thead>
       <tr>
        <th>Admission</th>
        <th>Student</th>
        <th>Mark /100</th>
        <th>Grade</th>
       </tr>
      </thead>
      <tbody id="resultsTable"></tbody>
     </table>
    </div>
   </section>

   <!-- ANALYSIS -->
   <section id="page-analysis" class="page hidden">
    <div class="page-title">
     <h2>Performance Analysis</h2>
     <button onclick="renderAnalysis()">Refresh Analysis</button>
    </div>

    <div class="panel">
     <div class="grid">
      <select id="analysisGrade" onchange="renderAnalysis()">
       <option value="">All Grades</option>
       <option>Grade 7</option>
       <option>Grade 8</option>
       <option>Grade 9</option>
      </select>

      <select id="analysisTerm" onchange="renderAnalysis()">
       <option>Term 1</option>
       <option>Term 2</option>
       <option>Term 3</option>
      </select>

      <input id="analysisYear" type="number" onchange="renderAnalysis()">
     </div>
    </div>

    <div class="cards">
     <div class="card"><h3>EE</h3><div id="countEE" class="number">0</div></div>
     <div class="card"><h3>ME</h3><div id="countME" class="number">0</div></div>
     <div class="card"><h3>AE</h3><div id="countAE" class="number">0</div></div>
     <div class="card"><h3>BE</h3><div id="countBE" class="number">0</div></div>
    </div>

    <div class="panel" style="margin-top:18px">
     <h3>Subject Performance</h3>
     <div class="table-wrap">
      <table>
       <thead>
        <tr>
         <th>Subject</th>
         <th>Entries</th>
         <th>Mean</th>
         <th>EE</th>
         <th>ME</th>
         <th>AE</th>
         <th>BE</th>
        </tr>
       </thead>
       <tbody id="analysisTable"></tbody>
      </table>
     </div>
    </div>
   </section>

   <!-- REPORTS -->
   <section id="page-reports" class="page hidden">
    <div class="page-title">
     <h2>Report Cards</h2>
     <button onclick="window.print()">🖨️ Print</button>
    </div>

    <div class="panel no-print">
     <div class="grid">
      <select id="reportGrade" onchange="loadReportStudents()">
       <option>Grade 7</option>
       <option>Grade 8</option>
       <option>Grade 9</option>
      </select>
      <select id="reportStudent"></select>
      <select id="reportTerm">
       <option>Term 1</option>
       <option>Term 2</option>
       <option>Term 3</option>
      </select>
      <input id="reportYear" type="number">
     </div>

     <div class="actions">
      <button onclick="generateReport()">Generate Report</button>
      <button onclick="printSelectedReport()">Print Report</button>
     </div>
    </div>

    <div id="reportArea"></div>
   </section>

   <!-- HISTORY -->
   <section id="page-history" class="page hidden">
    <div class="page-title">
     <h2>Results History</h2>
    </div>

    <div class="panel">
     <div class="grid">
      <select id="historyGrade" onchange="renderHistory()">
       <option value="">All Grades</option>
       <option>Grade 7</option>
       <option>Grade 8</option>
       <option>Grade 9</option>
      </select>
      <select id="historyTerm" onchange="renderHistory()">
       <option value="">All Terms</option>
       <option>Term 1</option>
       <option>Term 2</option>
       <option>Term 3</option>
      </select>
      <input id="historyYear" type="number" onchange="renderHistory()">
     </div>
    </div>

    <div class="panel table-wrap">
     <table>
      <thead>
       <tr>
        <th>Student</th>
        <th>Admission</th>
        <th>Grade</th>
        <th>Subject</th>
        <th>Mark</th>
        <th>Grade</th>
        <th>Term</th>
        <th>Year</th>
        <th>Status</th>
       </tr>
      </thead>
      <tbody id="historyTable"></tbody>
     </table>
    </div>
   </section>

   <!-- SETTINGS -->
   <section id="page-settings" class="page hidden">
    <div class="page-title">
     <h2>School Settings</h2>
    </div>

    <div class="panel">
     <div class="grid">
      <div>
       <label>School Name</label>
       <input id="schoolName">
      </div>
      <div>
       <label>UPI</label>
       <input id="schoolUPI">
      </div>
      <div>
       <label>Location</label>
       <input id="schoolLocation">
      </div>
      <div>
       <label>Phone</label>
       <input id="schoolPhone">
      </div>
      <div>
       <label>Email</label>
       <input id="schoolEmail">
      </div>
      <div>
       <label>Opening Date</label>
       <input id="openingDate" type="date">
      </div>
      <div>
       <label>Closing Date</label>
       <input id="closingDate" type="date">
      </div>
     </div>

     <div class="form-group">
      <label>Logo URL</label>
      <input id="schoolLogo" placeholder="Paste logo image URL">
     </div>

     <div class="actions">
      <button class="success" onclick="saveSettings()">Save School Settings</button>
     </div>
    </div>

    <div class="panel">
     <h3>Data Management</h3>
     <p>Use these options carefully.</p>
     <div class="actions">
      <button onclick="exportData()">Export Data</button>
      <button onclick="document.getElementById('importFile').click()">Import Data</button>
      <input id="importFile" type="file" accept=".json" class="hidden" onchange="importData(event)">
     </div>
    </div>
   </section>

  </main>
 </div>
</div>

<!-- MODAL -->
<div id="modal" class="modal hidden">
 <div class="modal-box">
  <div id="modalContent"></div>
 </div>
</div>

<script>
/* =========================
   DATA
========================= */

const DEFAULT_SUBJECTS = [
 {id:"SCI",name:"Integrated Science",grades:["Grade 7","Grade 8","Grade 9"]},
 {id:"AGR",name:"Agriculture",grades:["Grade 7","Grade 8","Grade 9"]},
 {id:"MATH",name:"Mathematics",grades:["Grade 7","Grade 8","Grade 9"]},
 {id:"ENG",name:"English",grades:["Grade 7","Grade 8","Grade 9"]},
 {id:"KIS",name:"Kiswahili",grades:["Grade 7","Grade 8","Grade 9"]},
 {id:"SST",name:"Social Studies",grades:["Grade 7","Grade 8","Grade 9"]},
 {id:"CRE",name:"CRE",grades:["Grade 7","Grade 8","Grade 9"]},
 {id:"TECH",name:"Pre/Technical Studies",grades:["Grade 7","Grade 8","Grade 9"]},
 {id:"CA",name:"Creative Arts",grades:["Grade 7","Grade 8","Grade 9"]}
];

const DEFAULT_TEACHERS = [
 {
  id:1,name:"Mr Kim",username:"teacher",phone:"",
  allocations:[
   "Agriculture - Grade 7",
   "Agriculture - Grade 8",
   "Agriculture - Grade 9",
   "Pre/Technical Studies - Grade 7",
   "Integrated Science - Grade 7",
   "Integrated Science - Grade 8"
  ]
 },
 {
  id:2,name:"Md Keziah",username:"keziah",phone:"",
  allocations:[
   "Mathematics - Grade 7",
   "Mathematics - Grade 8",
   "Mathematics - Grade 9",
   "CRE - Grade 7",
   "CRE - Grade 8",
   "Integrated Science - Grade 9"
  ]
 },
 {
  id:3,name:"Mr Collins",username:"collins",phone:"",
  allocations:[
   "English - Grade 7",
   "English - Grade 8",
   "English - Grade 9",
   "Pre/Technical Studies - Grade 8",
   "Pre/Technical Studies - Grade 9",
   "CRE - Grade 9"
  ]
 },
 {
  id:4,name:"Mr Jonah",username:"jonah",phone:"",
  allocations:[
   "Kiswahili - Grade 7",
   "Kiswahili - Grade 8",
   "Kiswahili - Grade 9",
   "Social Studies - Grade 7",
   "Social Studies - Grade 8",
   "Social Studies - Grade 9"
  ]
 },
 {
  id:5,name:"Mr Kanda",username:"kanda",phone:"",
  allocations:[
   "Creative Arts - Grade 7",
   "Creative Arts - Grade 8",
   "Creative Arts - Grade 9"
  ]
 }
];

function getData(key, fallback){
 const raw=localStorage.getItem(key);
 if(raw===null){
  localStorage.setItem(key,JSON.stringify(fallback));
  return structuredClone(fallback);
 }
 try{return JSON.parse(raw)}catch{return structuredClone(fallback)}
}

let students=getData("shammah_students",[]);
let teachers=getData("shammah_teachers",DEFAULT_TEACHERS);
let subjects=getData("shammah_subjects",DEFAULT_SUBJECTS);
let results=getData("shammah_results",[]);
let settings=getData("shammah_settings",{
 name:"SHAMMAH MISSION SCHOOL",
 upi:"",
 location:"Marakwet West, Kapsowar",
 phone:"",
 email:"aicshammahschool2025@gmail.com",
 logo:"",
 openingDate:"",
 closingDate:""
});
let academic=getData("shammah_academic",{
 year:new Date().getFullYear(),
 term:"Term 1"
});

let currentUser=null;

/* =========================
   LOGIN
========================= */

function login(){
 const u=document.getElementById("loginUsername").value.trim();
 const p=document.getElementById("loginPassword").value;

 let account=null;

 if(u==="admin" && p==="admin123"){
  account={role:"Director",username:u,name:"Director of Studies"};
 }

 if(u==="teacher" && p==="teacher123"){
  account={role:"Teacher",username:u,name:"Mr Kim"};
 }

 if(!account){
  document.getElementById("loginError").textContent="Invalid username or password.";
  return;
 }

 currentUser=account;

 document.getElementById("loginPage").classList.add("hidden");
 document.getElementById("app").classList.remove("hidden");
 document.getElementById("currentUser").textContent=
   account.name+" • "+account.role;

 refreshAll();
}

function logout(){
 currentUser=null;
 document.getElementById("app").classL
