# Dticke
<!DOCTYPE html>
<html lang="de">
<head>
<meta charset="UTF-8">
<title>Digital Ticket</title>

<style>
body{
    font-family: Arial, sans-serif;
    background:#1e3c8f;
    display:flex;
    justify-content:center;
    align-items:center;
    height:100vh;
    margin:0;
}

.ticket{
    width:420px;
    background:white;
    border-radius:18px;
    overflow:hidden;
    box-shadow:0 10px 25px rgba(0,0,0,0.3);
}

/* Header */
.header{
    background:linear-gradient(90deg,#4e73c7,#2a55a5);
    color:white;
    padding:20px;
    display:flex;
    align-items:center;
    gap:15px;
}

/* DT 3D Logo */
.logo{
    width:60px;
    height:60px;
    background:#fff;
    color:#2a55a5;
    font-weight:bold;
    font-size:28px;
    display:flex;
    justify-content:center;
    align-items:center;
    border-radius:10px;
    border:3px solid #2a55a5;
    box-shadow: 0 4px 10px rgba(0,0,0,0.3);
    text-shadow: 1px 1px 2px #888;
    transform: rotate(-3deg);
}

.title{
    font-size:24px;
    font-weight:bold;
}

/* Content */
.content{
    padding:25px;
    text-align:center;
}

.user{
    font-size:18px;
    font-weight:bold;
    margin-bottom:10px;
}

/* QR Code as image with border */
.qr{
    display:inline-block;
    padding:20px;
    border:3px solid #2a55a5;
    border-radius:15px;
    margin-bottom:20px;
    transition: transform 0.3s, box-shadow 0.3s;
}
.qr:hover{
    transform: scale(1.05);
    box-shadow: 0 8px 20px rgba(0,0,0,0.4);
}
.qr img{
    width:200px;
    height:200px;
    display:block;
}

/* Ticket number */
.number{
    margin-top:15px;
    font-size:18px;
    background:#f3f3f3;
    padding:10px;
    border-radius:8px;
}

/* moving bar */
.bar{
    height:6px;
    background:#ddd;
    margin:20px 0;
    overflow:hidden;
    border-radius:6px;
    position:relative;
}

.bar span{
    position:absolute;
    width:80px;
    height:100%;
    background:#2c8ad6;
    animation:move 2s linear infinite;
}

@keyframes move{
    0%{left:0;}
    50%{left:calc(100% - 80px);}
    100%{left:0;}
}

/* info */
.info{
    text-align:left;
    font-size:15px;
    line-height:1.8;
}

/* Train Track */
.train-track{
    position:relative;
    height:50px;
    margin-top:25px;
    background:#888;
    border-radius:6px;
    overflow:hidden;
}

/* Rails */
.train-track::before{
    content:"";
    position:absolute;
    top:10px;
    left:0;
    width:100%;
    height:5px;
    background:#444;
}

.train-track::after{
    content:"";
    position:absolute;
    top:35px;
    left:0;
    width:100%;
    height:5px;
    background:#444;
}

/* Train */
.train{
    position:absolute;
    bottom:5px;
    width:80px;
    height:30px;
    background:#222;
    border-radius:5px;
    animation:trainMove 6s linear infinite;
}

/* Windows */
.train::before{
    content:"";
    position:absolute;
    top:5px;
    left:5px;
    width:20px;
    height:15px;
    background:#00f5ff;
    border-radius:2px;
}

.train::after{
    content:"";
    position:absolute;
    top:5px;
    right:5px;
    width:20px;
    height:15px;
    background:#00f5ff;
    border-radius:2px;
}

/* Wheels */
.wheel-left, .wheel-right{
    position:absolute;
    bottom:-5px;
    width:10px;
    height:10px;
    background:#333;
    border-radius:50%;
}

.wheel-left{left:10px;}
.wheel-right{right:10px;}

@keyframes trainMove{
    0%{left:-100px;}
    100%{left:100%;}
}
</style>
</head>

<body>

<div class="ticket">

<div class="header">
    <div class="logo">DT</div>
    <div class="title">D-Ticket</div>
</div>

<div class="content">

    <div class="user">DeutschlandTicket</div>

    <!-- QR Code from image link -->
    <div class="qr">
        <img src="qrticket.jpg" alt="QR Code">
    </div>

    <div class="number">
        123456789
    </div>

    <div class="bar">
        <span></span>
    </div>

    <div class="info">
        <b>Ticketnutzer*in:</b> Max Mustermann<br>
        <b>Gültig von:</b> 01.04.2026 – 00:00 Uhr<br>
        <b>Gültig bis:</b> 01.05.2026 – 01:00 Uhr<br>
        <b>Klasse:</b> 2. Klasse<br>
        <b>Geltungsbereich:</b> Deutschlandweit
    </div>

    <!-- Train track with train -->
    <div class="train-track">
        <div class="train">
            <div class="wheel-left"></div>
            <div class="wheel-right"></div>
        </div>
    </div>

</div>

</div>

</body>
</html>
