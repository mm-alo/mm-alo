<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>Emmanuel M Alo – .NET Developer Badge</title>
<style>
 :root {
   --purple: #512BD4;
   --purple-2: #8a6cf0;
   --ink: #1b1b1f;
   --gray: #8a8886;
   --line: #e1dfdd;
   --chip: #f3f2f1;
 }
 * { box-sizing: border-box; margin: 0; padding: 0; }
 html, body { background: transparent; }
 body {
   min-height: 100vh;
   display: flex;
   justify-content: center;
   font-family: "Segoe UI", Arial, Helvetica, sans-serif;
 }
 .scene { position: relative; width: 500px; height: 1000px; flex: none; }
 .scene div, .scene span { position: absolute; }

 /* ---------- Lanyard ---------- */
 .strap {
   top: -40px; width: 60px; height: 377px;
   transform-origin: 50% 40px;
   background:
     repeating-linear-gradient(45deg, rgba(0,0,0,.08) 0 2px, transparent 2px 5px),
     linear-gradient(90deg, #3a1b9c, #512BD4 15%, #6d4ae8 50%, #512BD4 85%, #3a1b9c);
   filter: drop-shadow(0 4px 4px rgba(27,16,64,.3));
   overflow: hidden;
   color: #fff;
   font-size: 11px; font-weight: 700; letter-spacing: 1.5px;
   writing-mode: vertical-rl;
   white-space: nowrap;
   line-height: 60px;
   text-align: left;
   padding-top: 4px;
 }
 .strap::before, .strap::after {
   content: ""; position: absolute; top: 0; bottom: 0; width: 0;
   border-left: 1.5px dashed rgba(255,255,255,.5);
 }
 .strap::before { left: 5px; }
 .strap::after  { right: 5px; }
 .strap.left  { left: 100px; transform: rotate(-18.2deg); }
 .strap.right { left: 340px; transform: rotate(18.2deg); text-indent: -340px; }

 /* ---------- Metal clip ---------- */
 .metal {
   background: linear-gradient(135deg, #f4f4f6, #a9acb3 35%, #e9eaee 60%, #7d8088);
   border: 1px solid #6b6e76;
   filter: drop-shadow(0 4px 4px rgba(27,16,64,.3));
 }
 .plate { left: 205px; top: 298px; width: 90px; height: 36px; border-radius: 8px; }
 .plate::before {
   content: ""; position: absolute; left: 8px; right: 8px; top: 7px; height: 4px;
   border-radius: 2px; background: rgba(255,255,255,.6);
 }
 .plate::after {
   content: ""; position: absolute; left: 10px; top: 21px; width: 6px; height: 6px; border-radius: 50%;
   background: #8b8e96; box-shadow: 62px 0 0 #8b8e96;
 }
 .tab { left: 238px; top: 332px; width: 24px; height: 20px; border-radius: 5px; }
 .ring {
   left: 236px; top: 346px; width: 28px; height: 42px; border-radius: 14px;
   border: 5px solid #b9bbc2; box-shadow: inset 0 0 0 1px #fff, 0 0 0 1px #6b6e76;
   filter: drop-shadow(0 4px 4px rgba(27,16,64,.3));
   z-index: 5;
 }

 /* ---------- Badge ---------- */
 .badge {
   left: 60px; top: 355px; width: 380px; height: 590px;
   border-radius: 28px; overflow: hidden;
   background: linear-gradient(#fff, #f5f4fa);
   box-shadow: 0 18px 36px rgba(42,21,102,.38), inset 0 0 0 1px rgba(255,255,255,.8);
 }
 .badge > div, .badge > span { position: absolute; }
 .header {
   left: 0; top: 0; width: 380px; height: 120px;
   background: linear-gradient(135deg, var(--purple), var(--purple-2));
   overflow: hidden;
 }
 .header::before, .header::after { content: ""; position: absolute; border-radius: 50%; background: #fff; }
 .header::before { width: 170px; height: 170px; right: -125px; top: -70px; opacity: .09; }
 .header::after  { width: 110px; height: 110px; left: -30px; top: 60px; opacity: .07; }
 .slot { left: 150px; top: 14px; width: 80px; height: 12px; border-radius: 6px; background: rgba(42,21,102,.55); }
 .title { left: 0; width: 380px; top: 42px; text-align: center; color: #fff; font-size: 22px; font-weight: 700; letter-spacing: 3px; }
 .sub   { left: 0; width: 380px; top: 72px; text-align: center; color: rgba(255,255,255,.85); font-size: 10px; letter-spacing: 2px; }

 .ring-halo { left: 120px; top: 100px; width: 140px; height: 140px; border-radius: 50%; background: rgba(255,255,255,.55); }
 .photo {
   left: 124px; top: 104px; width: 132px; height: 132px; border-radius: 50%;
   border: 3px solid var(--purple); overflow: hidden;
   background: linear-gradient(#f3f2f1, #d9d6ea);
 }
 .photo i { position: absolute; background: #bdb8da; display: block; }
 .photo .head { left: 39px; top: 23px; width: 48px; height: 48px; border-radius: 50%; }
 .photo .body { left: -7px; top: 81px; width: 140px; height: 90px; border-radius: 70px 70px 0 0; }

 .name { left: 0; width: 380px; top: 255px; text-align: center; font-size: 28px; font-weight: 700; color: var(--ink); }
 .role {
   left: 120px; top: 294px; width: 140px; height: 26px; border-radius: 13px;
   background: var(--purple); color: #fff; font-size: 14px; font-weight: 600;
   text-align: center; line-height: 26px;
 }
 .divider { left: 30px; top: 338px; width: 320px; height: 1px; background: var(--line); }
 .label { font-size: 10px; font-weight: 700; letter-spacing: 2px; color: var(--gray); }

 .chip {
   height: 28px; padding: 0 14px 0 28px; border-radius: 14px;
   background: var(--chip); border: 1px solid var(--line);
   color: var(--purple); font-size: 13px; font-weight: 600; line-height: 26px; white-space: nowrap;
 }
 .chip::before {
   content: ""; position: absolute; left: 13px; top: 10px; width: 7px; height: 7px;
   border-radius: 50%; background: var(--purple);
 }

 /* Glass panel */
 .glass {
   left: 24px; top: 450px; width: 332px; height: 100px; border-radius: 18px;
   background: linear-gradient(135deg, rgba(255,255,255,.85), rgba(255,255,255,.55));
   border: 1px solid var(--line);
   backdrop-filter: blur(8px);
 }
 .qr {
   left: 36px; top: 460px; width: 80px; height: 80px; border-radius: 8px;
   background: #fff; border: 1px solid var(--line); overflow: hidden;
 }
 .qr .data {
   left: 8px; top: 8px; width: 62px; height: 62px;
   background:
     repeating-linear-gradient(90deg, var(--ink) 0 3px, transparent 3px 7px),
     repeating-linear-gradient(0deg, #fff 0 3px, transparent 3px 8px),
     repeating-linear-gradient(45deg, transparent 0 5px, var(--ink) 5px 7px);
 }
 .qr .f { width: 22px; height: 22px; background: #fff; }
 .qr .f::before { content: ""; position: absolute; inset: 0; border: 3px solid var(--ink); }
 .qr .f::after  { content: ""; position: absolute; inset: 7px; background: var(--ink); }
 .qr .f1 { left: 6px;  top: 6px; }
 .qr .f2 { right: 6px; top: 6px; }
 .qr .f3 { left: 6px;  bottom: 6px; }

 .emp-label { left: 136px; }
 .emp-id  { left: 136px; top: 481px; font-size: 19px; font-weight: 700; color: var(--purple); }
 .emp-val { left: 136px; top: 530px; font-size: 13px; font-weight: 600; color: var(--ink); transform: translateY(-100%); margin-top: 10px; }

 .footer {
   left: 0; top: 558px; width: 380px; height: 32px;
   background: linear-gradient(135deg, var(--purple), var(--purple-2));
   color: #fff; font-size: 11px; font-weight: 700; letter-spacing: 4px;
   text-align: center; line-height: 32px;
 }
 .gloss {
   left: 0; top: 0; width: 380px; height: 260px;
   background: linear-gradient(135deg, rgba(255,255,255,.35), rgba(255,255,255,0) 60%);
   clip-path: polygon(0 0, 100% 0, 0 100%);
   pointer-events: none;
 }
</style>
</head>
<body>
<div class="scene">

<!-- Lanyard -->
<div class="strap left">.NET • ASP.NET CORE • C# • AZURE • REACT • .NET • ASP.NET CORE • C# • AZURE • REACT</div>
<div class="strap right">.NET • ASP.NET CORE • C# • AZURE • REACT • .NET • ASP.NET CORE • C# • AZURE • REACT</div>
<div class="metal plate"></div>
<div class="metal tab"></div>

<!-- Badge -->
<div class="badge">
<div class="header"></div>
<div class="slot"></div>
<div class="title">DEVELOPER ACCESS</div>
<div class="sub">.NET CONF • ALL ACCESS PASS</div>

<div class="ring-halo"></div>
<div class="photo"><i class="head"></i><i class="body"></i></div>

<div class="name">Emmanuel M Alo</div>
<div class="role">.NET Developer</div>
<div class="divider"></div>

<div class="label" style="left:30px; top:350px;">SKILLS</div>
<div class="chip" style="left:30px;  top:370px;">ASP.NET Core</div>
<div class="chip" style="left:154px; top:370px;">C#</div>
<div class="chip" style="left:218px; top:370px;">React.js</div>
<div class="chip" style="left:30px;  top:406px;">SQL Server</div>
<div class="chip" style="left:142px; top:406px;">Azure</div>

<div class="glass"></div>
<div class="qr">
<div class="data"></div>
<div class="f f1"></div><div class="f f2"></div><div class="f f3"></div>
</div>
<div class="label emp-label" style="top:468px;">EMPLOYEE ID</div>
<div class="emp-id">EMP-0427-NET</div>
<div class="label emp-label" style="top:512px;">ACCESS LEVEL</div>
<div class="emp-val" style="top:540px;">ALL SESSIONS</div>

<div class="footer">BUILD • CODE • SHIP</div>
<div class="gloss"></div>
</div>

<!-- Ring over the badge slot -->
<div class="ring"></div>
</div>
</body>
</html>


<!---
mm-alo/mm-alo is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
