<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Emmanuel M Alo - .NET Developer Badge</title>

<style>

:root{
    --purple:#512BD4;
    --purple2:#7A5AF8;
    --text:#1d1d1f;
    --gray:#666;
    --line:#e5e5e5;
}

*{
    margin:0;
    padding:0;
    box-sizing:border-box;
}

body{
    background:#f5f5f7;
    min-height:100vh;
    display:flex;
    justify-content:center;
    align-items:flex-start;
    font-family:"Segoe UI",sans-serif;
}

.scene{
    width:560px;
    height:1100px;
    position:relative;
}

/* -------------------- */
/* LANYARD */
/* -------------------- */

.strap{
    position:absolute;
    top:-50px;
    width:90px;
    height:430px;

    background:
    repeating-linear-gradient(
        45deg,
        rgba(255,255,255,.08) 0px,
        rgba(255,255,255,.08) 2px,
        transparent 2px,
        transparent 6px
    ),
    linear-gradient(
        90deg,
        #32178f,
        #512BD4,
        #7A5AF8,
        #512BD4,
        #32178f
    );

    color:white;
    font-size:12px;
    font-weight:700;

    writing-mode:vertical-rl;
    letter-spacing:1px;

    overflow:hidden;

    box-shadow:
    0 10px 20px rgba(0,0,0,.15),
    inset 0 0 15px rgba(255,255,255,.15);
}

.left{
    left:105px;
    transform:rotate(-18deg);
}

.right{
    right:105px;
    transform:rotate(18deg);
}

.strap span{
    position:absolute;
    inset:0;
    line-height:90px;
    white-space:nowrap;
}

/* -------------------- */
/* CLIP */
/* -------------------- */

.clip{
    position:absolute;

    top:320px;
    left:50%;
    transform:translateX(-50%);

    width:120px;
    height:52px;

    border-radius:10px;

    background:
    linear-gradient(
        135deg,
        #fafafa,
        #b9bcc4,
        #f1f1f1,
        #81848b
    );

    border:1px solid #6a6d73;

    box-shadow:
        0 5px 16px rgba(0,0,0,.2);
}

.clip:before{
    content:"";

    position:absolute;

    top:12px;
    left:12px;
    right:12px;

    height:6px;
    border-radius:4px;

    background:rgba(255,255,255,.7);
}

.ring{
    position:absolute;

    top:365px;
    left:50%;
    transform:translateX(-50%);

    width:40px;
    height:65px;

    border-radius:30px;

    border:6px solid #b8bbc1;

    background:white;

    z-index:5;
}

/* -------------------- */
/* CARD */
/* -------------------- */

.badge{

    position:absolute;

    top:395px;
    left:50%;

    transform:translateX(-50%);

    width:420px;
    height:620px;

    overflow:hidden;

    border-radius:30px;

    background:
    linear-gradient(
        180deg,
        #ffffff,
        #f7f4ff
    );

    box-shadow:
        0 20px 40px rgba(0,0,0,.15);

}

/* Top */

.header{

    height:130px;

    background:
    linear-gradient(
        135deg,
        var(--purple),
        var(--purple2)
    );

    position:relative;
}

.header::before{
    content:'.NET';

    position:absolute;

    right:-20px;
    top:-30px;

    font-size:110px;
    font-weight:900;

    color:rgba(255,255,255,.07);
}

.header::after{
    content:'';

    position:absolute;

    width:220px;
    height:220px;

    border-radius:50%;

    background:rgba(255,255,255,.08);

    left:-80px;
    bottom:-130px;
}

.title{
    position:absolute;
    width:100%;
    top:35px;

    text-align:center;

    color:white;
    font-size:24px;
    font-weight:700;
    letter-spacing:3px;
}

.subtitle{
    position:absolute;
    width:100%;
    top:72px;

    text-align:center;

    color:rgba(255,255,255,.85);

    font-size:11px;
    letter-spacing:2px;
}

/* Photo */

.photo-wrap{

    position:absolute;

    top:85px;
    left:50%;

    transform:translateX(-50%);

    width:140px;
    height:140px;

    border-radius:50%;

    border:4px solid var(--purple);

    background:white;

    overflow:hidden;
}

.photo{
    width:100%;
    height:100%;

    background:
    linear-gradient(
        #ededed,
        #d3d3d3
    );
}

.photo:before{
    content:'';

    position:absolute;

    width:50px;
    height:50px;

    border-radius:50%;

    background:#bbb;

    left:45px;
    top:25px;
}

.photo:after{
    content:'';

    position:absolute;

    width:120px;
    height:75px;

    border-radius:75px 75px 0 0;

    background:#bbb;

    left:10px;
    top:80px;
}

.name{
    margin-top:120px;

    text-align:center;

    font-size:32px;
    font-weight:700;

    color:var(--text);
}

.role{

    margin:10px auto;

    width:170px;

    text-align:center;

    padding:8px 0;

    background:var(--purple);

    color:white;

    border-radius:20px;

    font-weight:600;
}

.github{

    text-align:center;

    color:#666;

    font-size:13px;
    font-weight:600;
}

/* skills */

.skills{

    margin-top:35px;

    display:flex;
    justify-content:center;
    flex-wrap:wrap;
    gap:10px;
}

.skill{

    padding:8px 14px;

    border-radius:16px;

    background:#efeaff;

    border:1px solid #d9ccff;

    color:var(--purple);

    font-weight:600;
    font-size:13px;
}

/* glass panel */

.panel{

    width:350px;
    height:120px;

    margin:35px auto;

    border-radius:20px;

    background:
    linear-gradient(
        135deg,
        rgba(255,255,255,.9),
        rgba(255,255,255,.6)
    );

    border:1px solid var(--line);

    position:relative;
}

.qr{
    position:absolute;
    left:20px;
    top:20px;

    width:80px;
    height:80px;

    background:
    repeating-conic-gradient(
        #222 0 25%,
        white 0 50%
    );

    background-size:18px 18px;
}

.id-label{
    position:absolute;
    left:120px;
    top:24px;

    font-size:11px;
    letter-spacing:2px;

    color:#777;
    font-weight:700;
}

.id-value{
    position:absolute;
    left:120px;
    top:50px;

    color:var(--purple);

    font-size:22px;
    font-weight:700;
}

/* hologram */

.hologram{

    position:absolute;

    right:20px;
    bottom:20px;

    width:65px;
    height:65px;

    border-radius:50%;

    background:
    linear-gradient(
        135deg,
        #512BD4,
        #00BCF2,
        #7FBA00,
        #FFB900
    );

    opacity:.35;
}

/* footer */

.footer{

    position:absolute;

    bottom:0;

    width:100%;
    height:38px;

    background:
    linear-gradient(
        135deg,
        var(--purple),
        var(--purple2)
    );

    color:white;

    text-align:center;

    line-height:38px;

    font-size:12px;
    font-weight:700;
    letter-spacing:4px;
}

</style>
</head>
<body>

<div class="scene">

    <div class="strap left">
        <span>.NET • ASP.NET CORE • C# • AZURE • REACT • .NET • ASP.NET CORE • C# • AZURE • REACT •</span>
    </div>

    <div class="strap right">
        <span>.NET • ASP.NET CORE • C# • AZURE • REACT • .NET • ASP.NET CORE • C# • AZURE • REACT •</span>
    </div>

    <div class="clip"></div>
    <div class="ring"></div>

    <div class="badge">

        <div class="header">
            <div class="title">.NET DEVELOPER</div>
            <div class="subtitle">MICROSOFT TECHNOLOGY STACK</div>
        </div>

        <div class="photo-wrap">
            <div class="photo"></div>
        </div>

        <div class="name">
            Emmanuel M Alo
        </div>

        <div class="role">
            .NET Developer
        </div>

        <div class="github">
            github.com/EmmanuelAlo
        </div>

        <div class="skills">
            <div class="skill">ASP.NET Core</div>
            <div class="skill">C#</div>
            <div class="skill">React.js</div>
            <div class="skill">SQL Server</div>
            <div class="skill">Azure</div>
        </div>

        <div class="panel">

            <div class="qr"></div>

            <div class="id-label">
                EMPLOYEE ID
            </div>

            <div class="id-value">
                EMP-0427-NET
            </div>

            <div class="hologram"></div>

        </div>

        <div class="footer">
            BUILD • CODE • SHIP
        </div>

    </div>

</div>

</body>
</html>
