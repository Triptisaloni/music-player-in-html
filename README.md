# music-player-in-html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Music Player</title>
    <style id="lightCss" media="">
    @import url('https://fonts.googleapis.com/css2?family=Roboto&display=swap');
    /* font-family: 'Roboto', sans-serif; */
    @import url('https://fonts.googleapis.com/css2?family=Rubik&display=swap');
    /* font-family: 'Rubik', sans-serif; */

    *{
        padding: 0;
        margin: 0;
        -webkit-tap-highlight-color: rgba(0,0,0,0);
        box-sizing: border-box;
        -webkit-user-select: none; /* Safari */        
        -moz-user-select: none; /* Firefox */
        -ms-user-select: none; /* IE10+/Edge */
        user-select: none; /* Standard */
    }

    body{
        overflow: hidden;
        padding: 0;
        margin: 0;
        -webkit-user-select: none;
        -moz-user-select: none;
        -ms-user-select: none;
        user-select: none;
    }

    ::-webkit-scrollbar {  /* Remove scrollbar space */
        width: 0px;
        background: transparent;
    }

    @font-face {
        font-family: HelveticaNormal;
        src: url("https://res.cloudinary.com/dp1xkuswt/raw/upload/v1597987314/Helvetica_uld9sz.ttf");
    }

    a{
        text-decoration: none;
    }

    a:hover{
        text-decoration: none;
    }

    input:focus, textarea:focus, select:focus{
        outline: none;
    }

    .flex{
        display: flex;
    }

    .hidden{
        display: none;
    }

    .invisible{
        transition: 1s;
        opacity: 0 !important;
    }

    img{
        object-fit: cover;
    }

    .z-1{
        display: inline-block;
        transform: rotate(90deg);
        margin-left: 4px;
        margin-right: 4px;
        font-size: 30px;
        padding-bottom: 4px;
    }

    .sd{
        overflow: hidden !important;
    }

    .blur{
        transition: all 0.2s ease;
    }

    .blur-in{
        opacity: 0;
    }

    .blur-out{
        opacity: 1;
    }

    /* Menu */

    .menu{
        /* background: #4fb9e1; */
        background: white;
        /* color: white; */
        color: #3f444f;
        height: 80px;
        font-family: 'Rubik', sans-serif;
        font-size: 20px;
        z-index: -2;
    }

    .menu-item-1{
        /* z-index: 10; */
        /* position: relative; */
        height: 40px;
        line-height: 50px;
        padding-top: 2px;
        width: 60px;
        text-align: center;
    }

    .menu-item-2{
        height: 40px;
        line-height: 50px;
        flex-grow: 1;
        text-align: center;
        font-size: 16px;
        margin-right: 60px;
    }

    .menu-item-3{
        height: 40px;
        line-height: 50px;
        padding-top: 2px;
        width: 60px;
        text-align: center;
    }

    .menu-icon{
        font-size: 22px;
    }

    .menu-icon-2{
        font-size: 22px;
    }

    /* Home Screen */

    .home-screen{
        margin-top: -30px;
        height: calc(100vh - 50px);
        background: white;
        overflow: hidden;
        overflow-y: scroll !important;
    }

    .home-heading-1{
        position: relative;
        font-family: 'Roboto', sans-serif;
        font-size: 30px;
        color: #363c46;
        margin-left: 20px;
        font-weight: 600;
    }

    .home-heading-2{
        font-family: 'Roboto', sans-serif;
        font-size: 16px;
        color: #363c46;
        margin-left: 20px;
        font-weight: 600;
        margin-top: 32px;
    }

    /* Popular this week */

    .h-SCROLL{
        width: 100%;
        overflow-x: scroll;
        margin-top: 12px;
    }

    .home-card-1{
        position: relative;
        margin-left: 20px;
        background: linear-gradient(45deg, #ffb791, #ff6a82);
        /* width: 80%; */
        border-radius: 20px;
        margin-top: 10px;
        margin-bottom: 32px;
        box-shadow: 0px 4px 11px #ffdbdb;
        transition: 0.2s;
    }

    .home-card-1:active{
        transition: 0.1s;
        transform: scale(1.01);
        opacity: 0.8;
    }

    .home-card-2{
        position: relative;
        margin-left: 20px;
        background: linear-gradient(45deg, #1c97c5, #39baeb);
        /* width: 80%; */
        border-radius: 20px;
        margin-top: 10px;
        margin-bottom: 32px;
        box-shadow: 0px 4px 11px #bdedff;
        transition: 0.2s;
    }

    .home-card-2:active{
        transition: 0.1s;
        transform: scale(1.01);
        opacity: 0.8;
    }

    .home-c--1{
        margin-top: 20px;
        margin-left: 20px;
        margin-bottom: 20px;
    }

    .home-c-1-img{
        height: 90px;
        width: 90px;
        border: 4px solid rgb(150 226 255 / 28%);
        border-radius: 20px;
    }

    .home-c-2{
        flex-direction: column;
        color: white;
        font-family: 'Roboto', sans-serif;
        flex-grow: 1;
        margin-left: 10px;
        width: calc(60px + 100px);
    }

    .home-c-2-1{
        font-size: 16px;
    }

    .home-c-2-2{
        font-size: 12px;
        color: rgb(255 255 255 / 90%);
        margin-top: 4px;
    }

    .home-c-2-3{
        color: rgb(255 255 255 / 0.80);
        font-size: 11px;
        margin-top: 4px;
    }

    .home-c-3{
        color: white;
        margin-right: 20px;
        padding-top: 10px;
    }

    .home-c--2{
        margin-left: 20px;
        margin-right: 20px;
        color: white;
        font-family: 'Roboto', sans-serif;
        background: rgb(255 255 255 / 20%);
        border-top-left-radius: 20px;
        border-top-right-radius: 20px;
        padding-top: 10px;
        padding-bottom: 10px;
    }

    .home-c-2--stats-c{
        align-items: center;
        flex: 1;
        flex-direction: column;
    }

    .home-c-2-s-I-c{
        font-size: 16px;
    }

    .home-c-2-S-VAL{
        margin-top: 4px;
        font-size: 11px;
    }

    .h-c-1-PLUS-1{
        max-width: 20px;
        min-width: 20px;
        margin-left: 0px;
        opacity: 0;
    }

    /* Made for you */

    .home-heading-3{
        font-family: 'Roboto', sans-serif;
        font-size: 16px;
        color: #363c46;
        margin-left: 20px;
        margin-bottom: 20px;
        font-weight: 600;
    }

    .section-3{
        width: 100%;
        overflow: hidden;
        overflow-x: scroll;
    }

    .sec-3-box{
        position: relative;
        flex-direction: column;
        margin-left: 20px;
        font-family: 'Roboto', sans-serif;
        /* background: linear-gradient(135deg, #e5f8ff, #ffffff); */
        border-radius: 20px;
        padding-top: 6px;
        padding-right: 6px;
        padding-left: 6px;
        padding-bottom: 10px;
        margin-bottom: 20px;
        /* box-shadow: 5px 5px 8px 0px #edfaff; */
        transition: 0.2s;
    }

    .sec-3-box:active{
        transition: 0.1s;
        opacity: 0.4;
    }

    .section-3-image{
        height: 120px;
        width: 120px;
        border-radius: 20px;
    }

    .sec-3--2{
        flex-direction: column;
        text-align: center;
        margin-top: 4px;
        margin-bottom: 2px;
    }

    .sec-3-b-1{
        font-size: 12px;
        font-family: 'Rubik', sans-serif;
        font-weight: 600;
        color: #384554;
    }

    .sec-3-b-2{
        font-size: 10px;
        font-family: 'Rubik', sans-serif;
        color: #62768e;
    }

    .sec-4-box{
        position: relative;
        flex-direction: column;
        margin-left: 20px;
        font-family: 'Roboto', sans-serif;
        /* background: linear-gradient(135deg, #ffeee7, #ffffff); */
        border-radius: 20px;
        padding-top: 6px;
        padding-right: 6px;
        padding-left: 6px;
        padding-bottom: 10px;
        margin-bottom: 20px;
        /* box-shadow: 5px 5px 8px 0px #ffeee6; */
        transition: 0.2s;
    }

    .sec-4-box:active{
        transition: 0.1s;
        opacity: 0.4;
    }

    .sec-5-box{
        position: relative;
        flex-direction: column;
        margin-left: 20px;
        font-family: 'Roboto', sans-serif;
        border-radius: 20px;
        padding-top: 6px;
        padding-right: 6px;
        padding-left: 6px;
        padding-bottom: 10px;
        margin-bottom: 20px;
        transition: 0.2s;
    }

    .sec-5-box:active{
        transition: 0.1s;
        opacity: 0.4;
    }

    .section-4-image{
        height: 90px;
        width: 90px;
        border: 2px solid #f1fbff;
        border-radius: 100px;
    }

    .s-ml-0{
        margin-left: 0px;
    }

    /* Side Menu */

    .side-menu{
        top: 0px;
        left: -100%;
        position: fixed;
        height: 100vh;
        width: 100%;
        background: rgb(139 128 249 / 1);
        transition: 1s;
        opacity: 0.2;
    }

    .side-container{
        display: flex;
        flex-direction: column;
        width: calc(100% - 40px);
        margin: auto;
    }

    .side-c-1{
        color: white;
        font-size: 24px;
        margin-top: 20px;
    }

    .mt-40{
        margin-top: 40px !important;
    }

    .side-c-2{
        font-family: 'Roboto', sans-serif;
        color: white;
        font-size: 16px;
        margin-top: 10px;
        background: rgb(125 73 255 / 0.80);
        padding: 12px;
        padding-left: 32px;
        padding-right: 32px;
        border-radius: 4px;
    }

    .side-L-icon{
        font-size: 20px;
        margin-left: 10px;
        margin-bottom: -4px;
    }

    .side-copy{
        font-family: 'Roboto', sans-serif;
        color: #ffffff;
        margin-left: 20px;
        margin-top: calc(100vh - 380px);
    }

    /* Music Screen */

    .tob-white{
        transition: 0s;
        color: white !important;
    }

    .top-to-bottom {
        position: relative;
        -webkit-transform: translateZ(0);
        transform: translateZ(0);
        -webkit-transition: color 1000ms;
        transition: color 1000ms;
        z-index: 0;
    }

    .top-to-bottom:before {
        content: "";
        position: absolute;
        z-index: -1;
        top: 0;
        left: 0;
        right: 0;
        bottom: 0;
        background: #4fb9e1;
        -webkit-transform: scaleY(0);
        transform: scaleY(0);
        -webkit-transform-origin: 50% 0%;
        transform-origin: 50% 0%;
        -webkit-transition-property: transform;
        transition-property: transform;
        -webkit-transition: 300ms ease-out;
        transition: 0.6s ease-out;
    }

    .top-to-bottom-2:before {
        -webkit-transform: scaleY(1);
        transform: scaleY(1);
    }

    .music-screen{
        top: 1800px;
        opacity: 0.2;
        position: fixed;
        left: 0px;
        height: calc(100vh - 50px);
        width: 100%;
        background: white;
        border-top-left-radius: 30px;
        border-top-right-radius: 30px;
    }

    /* Music Player Screen */

    .music-disk-con{
        height: 200px;
        width: 200px;
        margin: auto;
        margin-top: 60px;
        border-radius: 200px;
        background: url("https://s.yimg.com/ny/api/res/1.2/mI4rBxEF5Z0kiLUURrH3VQ--~A/YXBwaWQ9aGlnaGxhbmRlcjtzbT0xO3c9ODAw/https://media-mbst-pub-ue1.s3.amazonaws.com/creatr-uploaded-images/2020-01/c8fff8c0-3d09-11ea-b7ff-0f2094a2854d");
        background-position: center !important;
        background-repeat: no-repeat !important;
        background-size: cover !important;
        box-shadow: 5px 5px 8px 0px #ffeee6;
    }

    .music-h-1{
        text-align: center;
        margin-top: 20px;
        font-family: HelveticaNormal;
        font-size: 22px;
        font-weight: 600;
        color: #313742;
    }

    .music-h-2{
        text-align: center;
        margin-top: 6px;
        font-family: 'Rubik', sans-serif;
        font-size: 14px;
        color: #797b80;
    }

    .btn-container{
        width: 100%;
        text-align: center;
        font-size: 40px;
        margin-top: 40px;
        align-items: center;
        justify-content: center;
    }

    .f-32{
        font-size: 26px;
        color: #343a45;
    }

    .btn-2-box{
        padding: 8px;
        transition: 0.1s;
    }

    .btn-2-box:active{
        transition: 0.1s;
        opacity: 0.4;
    }

    .b-2-b-MID{
        color: #4fb9e1;
        filter: drop-shadow( 4px 8px 8px rgba(183, 218, 232, 0.6));
        margin-left: 32px;
        margin-right: 32px;

    }

    .bottom-btn{
        position: absolute;
        bottom: 0;
        width: 100%;
        align-items: center;
        justify-content: center;
        padding: 10px;
    }

    .bottom-btn-content{
        color: #84a4d6;
        font-size: 20px;
        margin-left: 20px;
        margin-right: 20px;
        width: 33%;
        text-align: center;
        transition: 0.1s;
    }

    .bottom-btn-content:active{
        transition: 0.1s;
        opacity: 0.2;
    }

    .b-b-c-MID{
        font-size: 26px;
        color: #FF8C61;
        filter: drop-shadow( 4px 4px 10px rgba(255, 140, 97, 0.6));
    }

    .inBack-container{
        opacity: 0;
    }

    .check-bottom-opt{
        color: #1c4d99;
    }

    .bottom-btn {
        display: none;
    }

    /* Splash Screen */

    .splash-screen{
        overflow: hidden;
        height: 100vh;
        width: 100%;
        position: fixed;
        top: 0;
        left: 0;
        background: white;
        display: flex;
        align-items: center;
        text-align: center;
        transition: all 1s ease;
    }

    .s-s-con-1{
        display: flex;
        width: 100%;
        justify-content: center;
        align-items: center;
    }

    .splash-ss-item-1{
        font-size: 28px;
        color: #363c46;
        margin-top: 6px;
    }

    .z-2{
        display: inline-block;
        transform: rotate(0deg);
        margin-left: 4px;
        margin-right: 4px;
        font-size: 30px;
        padding-bottom: 4px;
    }

    #zTwo{
        -webkit-transition: all 1s ease;
        -moz-transition: all 11s ease;
        -o-transition: all 1s ease;
        transition: all 1s ease;
    }

    /* Some Extra Styling */

    #myAudio {
        opacity: 0;
    }

    #songName2{
        color: white !important;
        -webkit-transition: all 1s ease;
        -moz-transition: all 11s ease;
        -o-transition: all 1s ease;
        transition: all 1s ease;
    }

    @media screen and (min-height: 480px) {
        .bottom-btn {
            display: flex;
        }
    }
    </style>
    <!-- Same stylesheet with darker colors -->
    <style id="darkCss" media="max-width=1px">
    @import url(https://fonts.googleapis.com/css2?family=Roboto&display=swap);@import url(https://fonts.googleapis.com/css2?family=Rubik&display=swap);*{padding:0;margin:0;-webkit-tap-highlight-color:transparent;box-sizing:border-box;-webkit-user-select:none;-moz-user-select:none;-ms-user-select:none;user-select:none}body{background:#0e0f1b;overflow:hidden;padding:0;margin:0;-webkit-user-select:none;-moz-user-select:none;-ms-user-select:none;user-select:none}::-webkit-scrollbar{width:0;background:0 0}@font-face{font-family:HelveticaNormal;src:url(https://res.cloudinary.com/dp1xkuswt/raw/upload/v1597987314/Helvetica_uld9sz.ttf)}a{text-decoration:none}a:hover{text-decoration:none}input:focus,select:focus,textarea:focus{outline:0}.flex{display:flex}.hidden{display:none}.invisible{opacity:0}img{object-fit:cover;filter: saturate(0.5);}.z-1{display:inline-block;transform:rotate(90deg);margin-left:4px;margin-right:4px;font-size:30px;padding-bottom:4px}.sd{overflow:hidden!important}.blur{transition:all .8s ease}.blur-in{opacity:0}.blur-out{opacity:1;}.menu{background:#0e0f1b;color:#3f444f;height:80px;font-family:Rubik,sans-serif;font-size:20px;z-index:-2}.menu-item-1{height:40px;line-height:50px;padding-top:2px;width:60px;text-align:center;color:#a2ace1}.menu-item-2{height:40px;line-height:50px;flex-grow:1;text-align:center;font-size:16px;margin-right:60px;color:#959fd6;}.menu-item-3{height:40px;line-height:50px;padding-top:2px;width:60px;text-align:center}.menu-icon{font-size:22px}.menu-icon-2{font-size:22px}.home-screen{margin-top:-30px;height:calc(100vh - 50px);background:#0e0f1b;overflow:hidden;overflow-y:scroll!important}.home-heading-1{position:relative;font-family:Roboto,sans-serif;font-size:30px;color:#cccddd;margin-left:20px;font-weight:500}.home-heading-2{font-family:Roboto,sans-serif;font-size:16px;color:#8186c6;margin-left:20px;font-weight:600;margin-top:32px}.h-SCROLL{width:100%;overflow-x:scroll;margin-top:12px}.home-card-1{position:relative;margin-left:20px;background:linear-gradient(45deg,#191b30,#131425);border-radius:20px;margin-top:10px;margin-bottom:32px;box-shadow:0 4px 11px #020204;transition:.2s}.home-card-1:active{transition:.1s;transform:scale(1.01);opacity:.8}.home-card-2{position:relative;margin-left:20px;background:linear-gradient(45deg,#151729,#0a0d21);border-radius:20px;margin-top:10px;margin-bottom:32px;box-shadow:0 4px 11px #020204;transition:.2s}.home-card-2:active{transition:.1s;transform:scale(1.01);opacity:.8}.home-c--1{margin-top:20px;margin-left:20px;margin-bottom:20px}.home-c-1-img{height:90px;width:90px;border:4px solid rgb(150 226 255 / 28%);border-radius:20px}.home-c-2{flex-direction:column;color:#fff;font-family:Roboto,sans-serif;flex-grow:1;margin-left:10px;width:calc(60px + 100px)}.home-c-2-1{font-size:16px}.home-c-2-2{font-size:12px;color:rgb(255 255 255 / 90%);margin-top:4px}.home-c-2-3{color:rgb(255 255 255 / .8);font-size:11px;margin-top:4px}.home-c-3{color:#fff;margin-right:20px;padding-top:10px}.home-c--2{margin-left:20px;margin-right:20px;color:#fff;font-family:Roboto,sans-serif;background:rgb(14 15 27 / 0.6);border-top-left-radius:20px;border-top-right-radius:20px;padding-top:10px;padding-bottom:10px}.home-c-2--stats-c{align-items:center;flex:1;flex-direction:column}.home-c-2-s-I-c{font-size:16px}.home-c-2-S-VAL{margin-top:4px;font-size:11px}.h-c-1-PLUS-1{max-width:20px;min-width:20px;margin-left:0;opacity:0}.home-heading-3{font-family:Roboto,sans-serif;font-size:16px;color:#8186c6;margin-left:20px;margin-bottom:20px;font-weight:600}.section-3{width:100%;overflow:hidden;overflow-x:scroll}.sec-3-box{position:relative;flex-direction:column;margin-left:20px;font-family:Roboto,sans-serif;border-radius:20px;padding-top:6px;padding-right:6px;padding-left:6px;padding-bottom:10px;margin-bottom:20px;transition:.2s}.sec-3-box:active{transition:.1s;opacity:.4}.section-3-image{height:120px;width:120px;border-radius:20px}.sec-3--2{flex-direction:column;text-align:center;margin-top:4px;margin-bottom:2px}.sec-3-b-1{font-size:12px;font-family:Rubik,sans-serif;font-weight:600;color:#ededee}.sec-3-b-2{font-size:10px;font-family:Rubik,sans-serif;color:#8183a1}.sec-4-box{position:relative;flex-direction:column;margin-left:20px;font-family:Roboto,sans-serif;border-radius:20px;padding-top:6px;padding-right:6px;padding-left:6px;padding-bottom:10px;margin-bottom:20px;transition:.2s}.sec-4-box:active{transition:.1s;opacity:.4}.sec-5-box{position:relative;flex-direction:column;margin-left:20px;font-family:Roboto,sans-serif;border-radius:20px;padding-top:6px;padding-right:6px;padding-left:6px;padding-bottom:10px;margin-bottom:20px;transition:.2s}.sec-5-box:active{transition:.1s;opacity:.4}.section-4-image{height:90px;width:90px;border:2px solid #4a4d7c;border-radius:100px}.s-ml-0{margin-left:0}.side-menu{top:0;left:-100%;position:fixed;height:100vh;width:100%;background:rgb(23 26 48 / 1);transition:1s;opacity:.2}.side-container{display:flex;flex-direction:column;width:calc(100% - 40px);margin:auto}.side-c-1{color:#fff;font-size:24px;margin-top:20px}.mt-40{margin-top:40px!important}.side-c-2{font-family:Roboto,sans-serif;color:#fff;font-size:16px;margin-top:10px;background:rgb(16 18 33);padding:12px;padding-left:32px;padding-right:32px;border-radius:4px}.side-L-icon{font-size:20px;margin-left:10px;margin-bottom:-4px}.side-copy{font-family:Roboto,sans-serif;color:#fff;margin-left:20px;margin-top:calc(100vh - 380px)}.tob-white{transition:0s;color:#0e0f1b!important}.top-to-bottom{position:relative;-webkit-transform:translateZ(0);transform:translateZ(0);-webkit-transition:color 1s;transition:color 1s;z-index:0}.top-to-bottom:before{content:"";position:absolute;z-index:-1;top:0;left:0;right:0;bottom:0;background:#191d32;-webkit-transform:scaleY(0);transform:scaleY(0);-webkit-transform-origin:50% 0;transform-origin:50% 0;-webkit-transition-property:transform;transition-property:transform;-webkit-transition:.3s ease-out;transition:.6s ease-out}.top-to-bottom-2:before{-webkit-transform:scaleY(1);transform:scaleY(1)}.music-screen{top:1800px;opacity:.2;position:fixed;left:0;height:calc(100vh - 50px);width:100%;background:#101327;border-top-left-radius:30px;border-top-right-radius:30px}.music-disk-con{height:200px;width:200px;margin:auto;margin-top:60px;border-radius:200px;background:url(https://s.yimg.com/ny/api/res/1.2/mI4rBxEF5Z0kiLUURrH3VQ--~A/YXBwaWQ9aGlnaGxhbmRlcjtzbT0xO3c9ODAw/https://media-mbst-pub-ue1.s3.amazonaws.com/creatr-uploaded-images/2020-01/c8fff8c0-3d09-11ea-b7ff-0f2094a2854d);background-position:center!important;background-repeat:no-repeat!important;background-size:cover!important;box-shadow:5px 5px 8px 0 #0b0d1b}.music-h-1{text-align:center;margin-top:20px;font-family:HelveticaNormal;font-size:22px;font-weight:600;color:#f2f3fc}.music-h-2{text-align:center;margin-top:6px;font-family:Rubik,sans-serif;font-size:14px;color:#797b80}.btn-container{width:100%;text-align:center;font-size:40px;margin-top:40px;align-items:center;justify-content:center}.f-32{font-size:26px;color:#8a94a6}.btn-2-box{padding:8px;transition:.1s}.btn-2-box:active{transition:.1s;opacity:.4}.b-2-b-MID{color:#45afd6;filter:drop-shadow( 4px 8px 8px rgba(183, 218, 232, .2));margin-left:32px;margin-right:32px}.bottom-btn{position:absolute;bottom:0;width:100%;align-items:center;justify-content:center;padding:10px}.bottom-btn-content{color:#84a4d6;font-size:20px;margin-left:20px;margin-right:20px;width:33%;text-align:center;transition:.1s}.bottom-btn-content:active{transition:.1s;opacity:.2}.b-b-c-MID{font-size:26px;color:#ff8c61;filter:drop-shadow( 4px 4px 10px rgba(255, 140, 97, .6))}.inBack-container{opacity:0}.check-bottom-opt{color:#fff}.bottom-btn{display:none}.splash-screen{overflow:hidden;height:100vh;width:100%;position:fixed;top:0;left:0;background:#fff;display:flex;align-items:center;text-align:center;transition:all 1s ease}.s-s-con-1{display:flex;width:100%;justify-content:center;align-items:center}.splash-ss-item-1{font-size:28px;color:#363c46;margin-top:6px}.z-2{display:inline-block;transform:rotate(0);margin-left:4px;margin-right:4px;font-size:30px;padding-bottom:4px}#zTwo{-webkit-transition:all 1s ease;-moz-transition:all 11s ease;-o-transition:all 1s ease;transition:all 1s ease}@media screen and (min-height:480px){.bottom-btn{display:flex}}
    </style>
    <!-- Overwriting styles bcuz of laziness -_- -->
    <style>
        .home-heading-2{
            font-weight: 500;
        }
        .home-heading-3{
            font-weight: 500;
        }
    </style>
    <script>
        alert("\nFollow Me and upvote if you liked\n\nAIMU ✌️\n");
        alert("\n\nIt also has Dark Mode\n\n");
    </script>
</head>
<body>

    <!-- Menu -->
    <div id="menu" class="menu top-to-bottom blur">
        <div class="flex menu-c">
            <div id="showSideMenu" class="menu-item-1">
                <ion-icon name="menu" class="menu-icon"></ion-icon>
            </div>
            <div id="goBackToHome" class="menu-item-1 hidden">
                <ion-icon name="arrow-back" class="menu-icon"></ion-icon>
            </div>
            <div id="songName2" class="menu-item-2 invisible">
                Song
            </div>
            <!-- <div class="menu-item-3">
                <ion-icon name="sunny" class="menu-icon-2"></ion-icon>
            </div> -->
        </div>
    </div>

    <!-- Home Screen -->
    <div id="homeScreen" class="home-screen blur">
        <div class="home-heading-1">
            Promu<span class="z-1">z</span>e
        </div>

        <div class="home-heading-2">
            Popular this week
        </div>

        <div id="hideOnMusic" class="flex h-SCROLL">

            <div class="home-card-1" onclick="playMusic({songImage: 'https:\/\/s.yimg.com/ny/api/res/1.2/mI4rBxEF5Z0kiLUURrH3VQ--~A/YXBwaWQ9aGlnaGxhbmRlcjtzbT0xO3c9ODAw/https:\/\/media-mbst-pub-ue1.s3.amazonaws.com/creatr-uploaded-images/2020-01/c8fff8c0-3d09-11ea-b7ff-0f2094a2854d', songName: 'Gurenge', songArtist: 'LiSA', songID: 'https:\/\/res.cloudinary.com/dp1xkuswt/video/upload/v1598754151/Gurenge_ykirrv.mp3'});">
                <div class="flex home-c--1">
                    <div class="home-c-1">
                        <img class="home-c-1-img" src="https://s.yimg.com/ny/api/res/1.2/mI4rBxEF5Z0kiLUURrH3VQ--~A/YXBwaWQ9aGlnaGxhbmRlcjtzbT0xO3c9ODAw/https://media-mbst-pub-ue1.s3.amazonaws.com/creatr-uploaded-images/2020-01/c8fff8c0-3d09-11ea-b7ff-0f2094a2854d">
                    </div>
                    <div class="flex home-c-2">
                        <div class="home-c-2-1">
                            Gurenge
                        </div>
                        <div class="home-c-2-2">
                            LiSA
                        </div>
                        <div class="home-c-2-3">
                            1:29
                        </div>
                    </div>
                    <div class="home-c-3">
                        <ion-icon name="play" class="home-c-3-1"></ion-icon>
                    </div>
                </div>
                <div class="flex home-c--2">
                    <div class="flex home-c-2--stats-c">
                        <div class="home-c-2-s-I-c">
                            <ion-icon name="play" class="home-c--2-ICON"></ion-icon>
                        </div>
                        <div class="home-c-2-S-VAL">
                            18M
                        </div>
                    </div>
                    <div class="flex home-c-2--stats-c">
                        <div class="home-c-2-s-I-c">
                            <ion-icon name="heart" class="home-c--2-ICON"></ion-icon>
                        </div>
                        <div class="home-c-2-S-VAL">
                            564K
                        </div>
                    </div>
                    <div class="flex home-c-2--stats-c">
                        <div class="home-c-2-s-I-c">
                            <ion-icon name="download" class="home-c--2-ICON"></ion-icon>
                        </div>
                        <div class="home-c-2-S-VAL">
                            12.2K
                        </div>
                    </div>
                    <div class="flex home-c-2--stats-c">
                        <div class="home-c-2-s-I-c">
                            <ion-icon name="arrow-redo" class="home-c--2-ICON"></ion-icon>
                        </div>
                        <div class="home-c-2-S-VAL">
                            16K
                        </div>
                    </div>
                </div>
            </div>

            <div class="home-card-2" onclick="playMusic({songImage: 'https:\/\/i1.sndcdn.com/artworks-000558667800-97icts-t500x500.jpg', songName: 'That\'s Why I Gave Up On Music', songArtist: 'yoshurika', songID: 'https:\/\/res.cloudinary.com/dp1xkuswt/video/upload/v1598754173/%E3%83%A8%E3%83%AB%E3%82%B7%E3%82%AB_-_%E3%81%A0%E3%81%8B%E3%82%89%E5%83%95%E3%81%AF%E9%9F%B3%E6%A5%BD%E3%82%92%E8%BE%9E%E3%82%81%E3%81%9F_Music_Video_afaeot.mp3'});">
                <div class="flex home-c--1">
                    <div class="home-c-1">
                        <img class="home-c-1-img" src="https://i1.sndcdn.com/artworks-000558667800-97icts-t500x500.jpg">
                    </div>
                    <div class="flex home-c-2">
                        <div class="home-c-2-1">
                            That's Why I...
                        </div>
                        <div class="home-c-2-2">
                            Yorushika
                        </div>
                        <div class="home-c-2-3">
                            4:06
                        </div>
                    </div>
                    <div class="home-c-3">
                        <ion-icon name="play" class="home-c-3-1"></ion-icon>
                    </div>
                </div>
                <div class="flex home-c--2">
                    <div class="flex home-c-2--stats-c">
                        <div class="home-c-2-s-I-c">
                            <ion-icon name="play" class="home-c--2-ICON"></ion-icon>
                        </div>
                        <div class="home-c-2-S-VAL">
                            42M
                        </div>
                    </div>
                    <div class="flex home-c-2--stats-c">
                        <div class="home-c-2-s-I-c">
                            <ion-icon name="heart" class="home-c--2-ICON"></ion-icon>
                        </div>
                        <div class="home-c-2-S-VAL">
                            812K
                        </div>
                    </div>
                    <div class="flex home-c-2--stats-c">
                        <div class="home-c-2-s-I-c">
                            <ion-icon name="download" class="home-c--2-ICON"></ion-icon>
                        </div>
                        <div class="home-c-2-S-VAL">
                            42K
                        </div>
                    </div>
                    <div class="flex home-c-2--stats-c">
                        <div class="home-c-2-s-I-c">
                            <ion-icon name="arrow-redo" class="home-c--2-ICON"></ion-icon>
                        </div>
                        <div class="home-c-2-S-VAL">
                            28K
                        </div>
                    </div>
                </div>
            </div>

            <div class="home-card-1 h-c-1-PLUS-1">
                ..
            </div>
        </div>

<!-- Made for you -->

        <div class="home-heading-3">
            Made for you
        </div>

        <div class="flex section-3">

            <div class="flex sec-3-box" onclick="playMusic({songImage: 'https:\/\/i1.sndcdn.com/artworks-000349221030-ektr17-t500x500.jpg', songName: 'Sparkle', songArtist: 'radwimpsstaff', songID: 'https:\/\/res.cloudinary.com/dp1xkuswt/video/upload/v1598754293/Sparkle_Your_Name_AMV_eakzyu.mp3'});">
                <div class="sec-3--1">
                    <img class="section-3-image" src="https://i1.sndcdn.com/artworks-000349221030-ektr17-t500x500.jpg">
                </div>
                <div class="flex sec-3--2">
                    <div class="sec-3-b-1">
                        Sparkle
                    </div>
                    <div class="sec-3-b-2">
                        radwimpsstaff
                    </div>
                </div>
            </div>

            <div class="flex sec-3-box" onclick="playMusic({songImage: 'https:\/\/i2.wp.com/www.kotilyrics.com/wp-content/uploads/2020/06/Marshmello-Halsey-Be-Kind-Lyrics.jpg?resize=400%2C400&ssl=1', songName: 'Be Kind', songArtist: 'H & M', songID: 'https:\/\/pagalworld.to/files/download/id/1151'});">
                <div class="sec-3--1">
                    <img class="section-3-image" src="https://i2.wp.com/www.kotilyrics.com/wp-content/uploads/2020/06/Marshmello-Halsey-Be-Kind-Lyrics.jpg?resize=400%2C400&ssl=1">
                </div>
                <div class="flex sec-3--2">
                    <div class="sec-3-b-1">
                        Be Kind
                    </div>
                    <div class="sec-3-b-2">
                        Marshmallo
                    </div>
                </div>
            </div>

            <div class="flex sec-3-box" onclick="playMusic({songImage: 'https:\/\/i.ytimg.com/vi/LAlzrCndEv8/maxresdefault.jpg', songName: 'Usotsuki', songArtist: 'Yorushika', songID: 'https:\/\/res.cloudinary.com/dp1xkuswt/video/upload/v1598754328/Yorushika_-_Usotsuki_A_Whisker_Away_ED_zdkfxa.mp3'});">
                <div class="sec-3--1">
                    <img class="section-3-image" src="https://i.ytimg.com/vi/LAlzrCndEv8/maxresdefault.jpg">
                </div>
                <div class="flex sec-3--2">
                    <div class="sec-3-b-1">
                        Usotsuki
                    </div>
                    <div class="sec-3-b-2">
                        Yorushika
                    </div>
                </div>
            </div>

            <!-- ERROR -->
            <div class="flex sec-3-box" onclick="playMusic({songImage: 'https:\/\/i.pinimg.com/originals/79/57/52/7957524c6be6cee0a16ac5ac129f1a9b.jpg', songName: '2002', songArtist: 'Anne-Marie', songID: 'https:\/\/res.cloudinary.com/dp1xkuswt/video/upload/v1598748429/Anne_Marie_2002_Lyrics-_youtube2mp3downloader.com_xuedb4.mp3'});">
                <div class="sec-3--1">
                    <img class="section-3-image" src="https://i.pinimg.com/originals/79/57/52/7957524c6be6cee0a16ac5ac129f1a9b.jpg">
                </div>
                <div class="flex sec-3--2">
                    <div class="sec-3-b-1">
                        2002
                    </div>
                    <div class="sec-3-b-2">
                        Anne-Marie
                    </div>
                </div>
            </div>

            <div class="flex sec-3-box" onclick="playMusic({songImage: 'https:\/\/i.pinimg.com/originals/07/9a/07/079a0778027a2c9c832cc7e206197043.jpg', songName: 'Unravel', songArtist: 'Toru Kitajima', songID: 'https:\/\/res.cloudinary.com/dp1xkuswt/video/upload/v1598754581/Tokyo_Ghoul_Opening_Theme_Unravel_cvwq91.mp3'});">
                <div class="sec-3--1">
                    <img class="section-3-image" src="https://i.pinimg.com/originals/07/9a/07/079a0778027a2c9c832cc7e206197043.jpg">
                </div>
                <div class="flex sec-3--2">
                    <div class="sec-3-b-1">
                        Unravel
                    </div>
                    <div class="sec-3-b-2">
                        Toru Kitajima
                    </div>
                </div>
            </div>

            <!-- ERROR -->
            <div class="flex sec-3-box" onclick="playMusic({songImage: 'https:\/\/m.media-amazon.com/images/I/614wnBXWiBL._SS500_.jpg', songName: 'End of Time', songArtist: 'K-391', songID: 'https:\/\/res.cloudinary.com/dp1xkuswt/video/upload/v1598749751/K-391_Alan_Walker_Ahrix_-_End_of_Time_Official_Video_r47t8l.mp3'});">
                <div class="sec-3--1">
                    <img class="section-3-image" src="https://m.media-amazon.com/images/I/614wnBXWiBL._SS500_.jpg">
                </div>
                <div class="flex sec-3--2">
                    <div class="sec-3-b-1">
                        End of Time
                    </div>
                    <div class="sec-3-b-2">
                        K-391
                    </div>
                </div>
            </div>

            <div class="flex sec-3-box h-c-1-PLUS-1">
            </div>

        </div>

<!-- English Songs -->

        <div class="home-heading-3">
            English Songs
        </div>

        <div class="flex section-3">

            <div class="flex sec-4-box" onclick="playMusic({songImage: 'https:\/\/i.pinimg.com/originals/b5/49/88/b549885a5990d32450cb6ee68a3215de.jpg', songName: 'Galway Girl', songArtist: 'Ed Sheeran', songID: 'https:\/\/res.cloudinary.com/dp1xkuswt/video/upload/v1598750359/Ed_Sheeran_-_Galway_Girl_Official_Video_1_u67bnt.mp3'});">
                <div class="sec-3--1">
                    <img class="section-3-image" src="https://i.pinimg.com/originals/b5/49/88/b549885a5990d32450cb6ee68a3215de.jpg">
                </div>
                <div class="flex sec-3--2">
                    <div class="sec-3-b-1">
                        Galway Girl
                    </div>
                    <div class="sec-3-b-2">
                        Ed Sheeran
                    </div>
                </div>
            </div>

            <div class="flex sec-4-box" onclick="playMusic({songImage: 'https:\/\/images.genius.com/ad592b4635299a1819a8c5a0073fee73.1000x1000x1.jpg', songName: 'When I Grow Up', songArtist: 'NF', songID: 'https:\/\/res.cloudinary.com/dp1xkuswt/video/upload/v1598751039/NF_-_When_I_Grow_Up_kwrp5t.mp3'});">
                <div class="sec-3--1">
                    <img class="section-3-image" src="https://images.genius.com/ad592b4635299a1819a8c5a0073fee73.1000x1000x1.jpg">
                </div>
                <div class="flex sec-3--2">
                    <div class="sec-3-b-1">
                        When I Grow Up
                    </div>
                    <div class="sec-3-b-2">
                        NF
                    </div>
                </div>
            </div>

            <div class="flex sec-4-box" onclick="playMusic({songImage: 'https:\/\/i1.sndcdn.com/artworks-000358980543-s6q5gr-t500x500.jpg', songName: 'Remembering', songArtist: 'Yutaka-Yamada', songID: 'https:\/\/res.cloudinary.com/dp1xkuswt/video/upload/v1598754655/OFFICIAL_AMV_-_Yutaka_Yamada_-_Remembering_from_Tokyo_Ghoul_re_%E3%82%84%E3%81%BE%E3%81%A0%E8%B1%8A_-_%E6%9D%B1%E4%BA%AC%E5%96%B0%E7%A8%AE_re_Tate_McRae_s3eznp.mp3'});">
                <div class="sec-3--1">
                    <img class="section-3-image" src="https://i1.sndcdn.com/artworks-000358980543-s6q5gr-t500x500.jpg">
                </div>
                <div class="flex sec-3--2">
                    <div class="sec-3-b-1">
                        Remembering
                    </div>
                    <div class="sec-3-b-2">
                        Yutaka-Yamada
                    </div>
                </div>
            </div>

            <div class="flex sec-4-box" onclick="playMusic({songImage: 'https:\/\/www.directlyrics.com/img/upload/anne-marie-friends-video-youtube.jpg', songName: 'FRIENDS', songArtist: 'Marshmallo', songID: 'https:\/\/res.cloudinary.com/dp1xkuswt/video/upload/v1598752703/Marshmello_Anne-Marie_-_FRIENDS_OFFICIAL_FRIENDZONE_ANTHEM_j5hybf.mp3'});">
                <div class="sec-3--1">
                    <img class="section-3-image" src="https://www.directlyrics.com/img/upload/anne-marie-friends-video-youtube.jpg">
                </div>
                <div class="flex sec-3--2">
                    <div class="sec-3-b-1">
                        FRIENDS
                    </div>
                    <div class="sec-3-b-2">
                        Marshmallo
                    </div>
                </div>
            </div>

            <div class="flex sec-4-box" onclick="playMusic({songImage: 'https:\/\/m.media-amazon.com/images/I/61O2SRKg6lL._SS500_.jpg', songName: 'COPYCAT', songArtist: 'Billie Eilish', songID: 'https:\/\/res.cloudinary.com/dp1xkuswt/video/upload/v1598752832/Billie_Eilish_-_COPYCAT_n47q0y.mp3'});">
                <div class="sec-3--1">
                    <img class="section-3-image" src="https://m.media-amazon.com/images/I/61O2SRKg6lL._SS500_.jpg">
                </div>
                <div class="flex sec-3--2">
                    <div class="sec-3-b-1">
                        COPYCAT
                    </div>
                    <div class="sec-3-b-2">
                        Billie Eilish
                    </div>
                </div>
            </div>

            <div class="flex sec-4-box" onclick="playMusic({songImage: 'https:\/\/www.edsheeran.com/sites/g/files/g2000006291/f/201906/BP-thumb-video-square.jpg', songName: 'Beautiful People', songArtist: 'Ed Sheeran', songID: 'https:\/\/res.cloudinary.com/dp1xkuswt/video/upload/v1598752906/Ed_Sheeran_-_Beautiful_People_feat._Khalid_Official_jx7l5y.mp3'});">
                <div class="sec-3--1">
                    <img class="section-3-image" src="https://www.edsheeran.com/sites/g/files/g2000006291/f/201906/BP-thumb-video-square.jpg">
                </div>
                <div class="flex sec-3--2">
                    <div class="sec-3-b-1">
                        Beautiful People
                    </div>
                    <div class="sec-3-b-2">
                        Ed Sheeran
                    </div>
                </div>
            </div>

            <div class="flex sec-3-box h-c-1-PLUS-1">
            </div>

        </div>

        <div class="home-heading-3">
            Artists
        </div>

        <div class="flex section-3">

            <div class="flex sec-5-box">
                <div class="sec-3--1">
                    <img class="section-4-image" src="https://i.pinimg.com/originals/18/1b/7a/181b7a42ca18e1989239425b93f5c83b.jpg">
                </div>
                <div class="flex sec-3--2">
                    <div class="sec-3-b-1">
                        Ed Sheeran
                    </div>
                </div>
            </div>

            <div class="flex sec-5-box">
                <div class="sec-3--1">
                    <img class="section-4-image" src="https://yt3.ggpht.com/a/AATXAJyD8SYdT_Rg-adPJZlfdZlzXXXjE23fk_xkI078=s100-c-k-c0xffffffff-no-rj-mo">
                </div>
                <div class="flex sec-3--2">
                    <div class="sec-3-b-1">
                        Yoshurika
                    </div>
                </div>
            </div>

            <div class="flex sec-5-box">
                <div class="sec-3--1">
                    <img class="section-4-image" src="https://yt3.ggpht.com/a/AATXAJyYwdrvyu-OxhtiG3Ju3Wocuy07xT64dW22NGTH4Q=s100-c-k-c0xffffffff-no-rj-mo">
                </div>
                <div class="flex sec-3--2">
                    <div class="sec-3-b-1">
                        Marshmello
                    </div>
                </div>
            </div>

            <div class="flex sec-5-box">
                <div class="sec-3--1">
                    <img class="section-4-image" src="https://yt3.ggpht.com/a/AATXAJwS-EfJzU6v3dqTzjkxpTZOnwUiPKtbB89Y8JpOQw=s100-c-k-c0xffffffff-no-rj-mo">
                </div>
                <div class="flex sec-3--2">
                    <div class="sec-3-b-1">
                        Eminem
                    </div>
                </div>
            </div>

            <div class="flex sec-5-box">
                <div class="sec-3--1">
                    <img class="section-4-image" src="https://yt3.ggpht.com/a/AATXAJwecJ214xgTGgLK7sGod-j9tlY5vClP-pdlm91A0w=s100-c-k-c0xffffffff-no-rj-mo">
                </div>
                <div class="flex sec-3--2">
                    <div class="sec-3-b-1">
                        radwimpsstaff
                    </div>
                </div>
            </div>

            <div class="flex sec-5-box">
                <div class="sec-3--1">
                    <img class="section-4-image" src="https://yt3.ggpht.com/a/AATXAJxQuKjkILwNh928PJPBTKEr9c2FNLBcflE5y78YSA=s100-c-k-c0xffffffff-no-rj-mo">
                </div>
                <div class="flex sec-3--2">
                    <div class="sec-3-b-1">
                        Anne-Marie
                    </div>
                </div>
            </div>

            <div class="flex sec-3-box h-c-1-PLUS-1 s-ml-0">
            </div>

        </div>

        <div class="home-heading-3">
            Anime Songs
        </div>

        <div class="flex section-3">

            <div class="flex sec-4-box" onclick="playMusic({songImage: 'https:\/\/i1.sndcdn.com/artworks-000569893652-pgwots-t500x500.jpg', songName: 'Grand Escape', songArtist: 'radwimpsstaff', songID: 'https:\/\/res.cloudinary.com/dp1xkuswt/video/upload/v1598754740/Full_Ver._Weathering_With_You_-_Grand_Escape_MV_zllpbn.mp3'});">
                <div class="sec-3--1">
                    <img class="section-3-image" src="https://i1.sndcdn.com/artworks-000569893652-pgwots-t500x500.jpg">
                </div>
                <div class="flex sec-3--2">
                    <div class="sec-3-b-1">
                        Grand Escape
                    </div>
                    <div class="sec-3-b-2">
                        radwimpsstaff
                    </div>
                </div>
            </div>

            <div class="flex sec-4-box" onclick="playMusic({songImage: 'https:\/\/i1.sndcdn.com/artworks-000237910600-2kuvqh-t500x500.jpg', songName: 'Say it', songArtist: 'yoshurika', songID: 'https:\/\/res.cloudinary.com/dp1xkuswt/video/upload/v1598754921/%E3%83%A8%E3%83%AB%E3%82%B7%E3%82%AB_-_%E8%A8%80%E3%81%A3%E3%81%A6_Music_Video_zlvste.mp3'});">
                <div class="sec-3--1">
                    <img class="section-3-image" src="https://i1.sndcdn.com/artworks-000237910600-2kuvqh-t500x500.jpg">
                </div>
                <div class="flex sec-3--2">
                    <div class="sec-3-b-1">
                        Say it
                    </div>
                    <div class="sec-3-b-2">
                        yoshurika
                    </div>
                </div>
            </div>

            <div class="flex sec-4-box" onclick="playMusic({songImage: 'https:\/\/cdna.artstation.com/p/assets/images/images/002/235/712/large/miura-naoko-kanainkd.jpg?1459109201', songName: 'Next to you', songArtist: 'NSZX', songID: 'https:\/\/res.cloudinary.com/dp1xkuswt/video/upload/v1598754820/Parasyte_-_Next_To_You_Anime_Version_nllg2e.mp3'});">
                <div class="sec-3--1">
                    <img class="section-3-image" src="https://cdna.artstation.com/p/assets/images/images/002/235/712/large/miura-naoko-kanainkd.jpg?1459109201">
                </div>
                <div class="flex sec-3--2">
                    <div class="sec-3-b-1">
                        Next to you
                    </div>
                    <div class="sec-3-b-2">
                        NSZX
                    </div>
                </div>
            </div>

            <div class="flex sec-4-box" onclick="playMusic({songImage: 'https:\/\/i1.sndcdn.com/artworks-000189644919-2uf2cs-t500x500.jpg', songName: 'Nandemonaiya', songArtist: 'radwimpsstaff', songID: 'https:\/\/res.cloudinary.com/dp1xkuswt/video/upload/v1598754951/Nandemonaiya_-_movie_ver._pvby7o.mp3'});">
                <div class="sec-3--1">
                    <img class="section-3-image" src="https://i1.sndcdn.com/artworks-000189644919-2uf2cs-t500x500.jpg">
                </div>
                <div class="flex sec-3--2">
                    <div class="sec-3-b-1">
                        Nandemonaiya
                    </div>
                    <div class="sec-3-b-2">
                        radwimpsstaff
                    </div>
                </div>
            </div>

            <div class="flex sec-4-box" onclick="playMusic({songImage: 'https:\/\/i1.sndcdn.com/artworks-000095244955-qr7is8-t500x500.jpg', songName: 'Let Me Hear', songArtist: 'Fear', songID: 'https:\/\/res.cloudinary.com/dp1xkuswt/video/upload/v1598755455/Parasyte_-_Let_Me_Hear_Romaji_English_37_je9tno.mp3'});">
                <div class="sec-3--1">
                    <img class="section-3-image" src="https://i1.sndcdn.com/artworks-000095244955-qr7is8-t500x500.jpg">
                </div>
                <div class="flex sec-3--2">
                    <div class="sec-3-b-1">
                        Let Me Hear
                    </div>
                    <div class="sec-3-b-2">
                        Fear
                    </div>
                </div>
            </div>

            <div class="flex sec-4-box" onclick="playMusic({songImage: 'https:\/\/i1.sndcdn.com/artworks-000332504310-4nz5qq-t500x500.jpg', songName: 'Asphyxia', songArtist: 'Cö shu Nie', songID: 'https:\/\/res.cloudinary.com/dp1xkuswt/video/upload/v1598755280/Asphyxia___Tokyo_Ghoul_fr_s7lnam.mp3'});">
                <div class="sec-3--1">
                    <img class="section-3-image" src="https://i1.sndcdn.com/artworks-000332504310-4nz5qq-t500x500.jpg">
                </div>
                <div class="flex sec-3--2">
                    <div class="sec-3-b-1">
                        Asphyxia
                    </div>
                    <div class="sec-3-b-2">
                        Cö shu Nie
                    </div>
                </div>
            </div>

            <div class="flex sec-3-box h-c-1-PLUS-1">
            </div>

        </div>

    </div>
    
    <!-- Music Screen -->
    <div id="musicScreen" class="music-screen">

        <div id="musicImage" class="music-disk-con">
            <div id="btnCircleHandle" class="music-disk-con-2"></div>
        </div>

        <div id="musicName" class="music-h-1">
            Gurenge
        </div>

        <div id="musicArtist" class="music-h-2">
            LiSA
        </div>

        <div id="audioHandler1" class="flex btn-container">
            <div class="btn-2-box f-32">
                <ion-icon class="btn-2-content-icon" name="play-back"></ion-icon>
            </div>
            <div class="btn-2-box b-2-b-MID">
                <ion-icon id="audioPlay" class="btn-2-content-icon" name="play"></ion-icon>
                <ion-icon id="audioPause" class="btn-2-content-icon hidden" name="pause"></ion-icon>
            </div>
            <div class="btn-2-box f-32">
                <ion-icon class="btn-2-content-icon" name="play-forward"></ion-icon>
            </div>
        </div>

        <div id="audioHandler2" class="flex btn-container">
            <div class="btn-2-box f-32">
                <ion-icon class="btn-2-content-icon" name="play-back"></ion-icon>
            </div>
            <div class="btn-2-box b-2-b-MID">
                <ion-icon id="audioPlay2" class="btn-2-content-icon" name="play"></ion-icon>
                <ion-icon id="audioPause2" class="btn-2-content-icon hidden" name="pause"></ion-icon>
            </div>
            <div class="btn-2-box f-32">
                <ion-icon class="btn-2-content-icon" name="play-forward"></ion-icon>
            </div>
        </div>

        <div class="flex bottom-btn">
            <div id="loopStatus" name="loopOff" class="bottom-btn-content">
                <ion-icon id="audioLoop" name="infinite" class="bottom-btn-s-icon"></ion-icon>
            </div>
            <div id="heartStatus" name="hUn" class="bottom-btn-content b-b-c-MID">
            <ion-icon id="heartUncheck" name="heart-outline" class="bottom-btn-icon"></ion-icon>
            <ion-icon id="heartCheck" name="heart" class="bottom-btn-icon hidden"></ion-icon>
            </div>
            <div id="repeatStatus" name="repeatOff" class="bottom-btn-content">
                <ion-icon id="audioRepeat" name="repeat" class="bottom-btn-s-icon"></ion-icon>
            </div>
        </div>

    </div>

    <!-- Side Menu -->
    <div id="sideMenu" class="side-menu">
        <div class="side-container">

            <div id="closeSideMenu" class="side-c-1">
                <ion-icon class="side-c-1-icon" name="arrow-back"></ion-icon>
            </div>

            <a href="https://www.sololearn.com/Profile/17904120/?ref=app" target="_blank">
                <div class="side-c-2 mt-40">
                    Follow Me
                </div>
            </a>

            <a href="https://www.instagram.com/codeninja02/" target="_blank">
            <div class="side-c-2">
                Visit my Instagram
            </div>
            </a>

            <div class="side-c-2 closeSM">
                Updates
            </div>

            <div class="side-c-2 closeSM">
                Notifications
            </div>

            <div id="switchMode" class="side-c-2">
                <span id="modeStatus" name="light">Light Mode</span> <ion-icon id="lightModeIcon" name="sunny" class="side-L-icon"></ion-icon><ion-icon id="darkModeIcon" name="sunny-outline" class="side-L-icon hidden"></ion-icon>
            </div>
        </div>

        <div class="side-copy">
            &copy; Programmer
        </div>
    </div>

    <div id="splashScreen" class="splash-screen">
        <div class="flex s-s-con-1">
            <!-- <div class="splash-ss-item-1">
                <ion-icon name="musical-notes"></ion-icon>
            </div> -->
            <div>
                <div class="home-heading-1">
                    Promu<span id="zTwo" class="z-2">z</span>e
                </div>
            </div>
        </div>
    </div>

    <audio id="audioEl">
        <source id="audioElSource" src="" type="audio/mpeg">
    </audio>

    <script src="https://code.jquery.com/jquery-3.5.1.min.js" integrity="sha256-9/aliU8dGd2tb6OSsuzixeV4y/faTqgFtohetphbbj0=" crossorigin="anonymous"></script>
    <script>
        var logger=function(){var o=null,n={enableLogger:function(){null!=o&&(window.console.log=o)},disableLogger:function(){o=console.log,window.console.log=function(){}}};return n}();$(document).ready(function(){logger.disableLogger()});
    </script>
    <script type="module" src="https://unpkg.com/ionicons@5.1.0/dist/ionicons/ionicons.esm.js"></script>
    <script>
        var audioEl = document.getElementById("audioEl");

        function showSideMenu() {
            $("#homeScreen").animate({
                
            }, 400).addClass("sd");
            $("#sideMenu").animate({
                left: 0,
                opacity: 1
            }, 100);

            $("#menu").addClass('blur-in');
            $("#homeScreen").addClass('blur-in');
        }

        function hideSideMenu() {
            $("#homeScreen").animate({
                
            }, 400).removeClass("sd");
            $("#sideMenu").animate({
                left: 0 - $(document).width(),
                opacity: 0.2
            }, 100);

            $("#menu").removeClass('blur-in');
            $("#homeScreen").removeClass('blur-in');
        }

        function showHome() {

            $("#homeScreen").animate({ scrollTop: 0 }, 100);

            $("#homeScreen").animate({
                opacity: 1
            }, 400).addClass("sd");
            $("#musicScreen").animate({
                top: 1800,
                opacity: 0.2
            }, 400);

            $("#songName2").addClass("invisible");
            bottomToTop();
            
        }

        function showMusic() {

            $("#homeScreen").animate({ scrollTop: 0 }, 100);

            $("#homeScreen").animate({
                // opacity: 0.2
            }, 400).removeClass("sd");
            $("#musicScreen").animate({
                top: 50,
                opacity: 1
            }, 400);

            topToBottom();
            hideSideMenu();

        }

        function fadeEffect(el){

            $(el).animate({
                opacity: 0
            }, 200).animate({
                opacity: 1
            }, 200);

        }

        $("#closeSideMenu").on("click", function(){
            hideSideMenu();
        });

        $("#showSideMenu").on("click", function(){
            showSideMenu();
        });

        $("#switchMode").on("click", function(){
            let modeStatus = $("#modeStatus").attr("name");

            if(modeStatus == "light"){
                $("#lightCss").attr("media", "max-width=1px");
                $("#darkCss").attr("media", "");
                $("#modeStatus").attr("name", "dark");
                $("#modeStatus").text("Dark Mode");
                $("#lightModeIcon").addClass("hidden");
                $("#darkModeIcon").removeClass("hidden");
                // fadeEffect("#switchMode");
            } else if(modeStatus == "dark"){
                $("#lightCss").attr("media", "");
                $("#darkCss").attr("media", "max-width=1px");
                $("#modeStatus").attr("name", "light");
                $("#modeStatus").text("Light Mode");
                $("#darkModeIcon").addClass("hidden");
                $("#lightModeIcon").removeClass("hidden");
                // fadeEffect("#switchMode");
            } else {
                hideSideMenu();
            }

            // hideSideMenu();

        });

        $(".closeSM").on("click", function(){
            hideSideMenu();
        });

        // Music Player Here

        $("#goBackToHome").on("click", function(){
            try {
                showHome();
                pauseAudio();
                // $("#hideOnMusic").css(
                //     "opacity", "1"
                // );
                $("#hideOnMusic").removeClass("invisible");
                if(audioStatus == true){
                    handleAudio();
                }
            } catch (error) {
                
            }
        });

        $(".menu").css("z-index", "0");

        function topToBottom(){
            $(".menu").addClass("top-to-bottom-2");
            $(".menu").addClass("tob-white");
            $(".menu").delay(200).css("z-index", "0");

            /*
            $(".menu").delay(400).queue(function(next) {
                $(this).css("z-index", "0"); 
                next(); 
            });
            */

            $("#showSideMenu").addClass("hidden");
            $("#goBackToHome").removeClass("hidden");
            $("#songName").removeClass("invisible");
            uncheckHeart();
        }

        function bottomToTop(){
            $(".menu").removeClass("top-to-bottom-2");
            $(".menu").removeClass("tob-white");

            // $(".menu").delay(2000).css("z-index", "-1");

            /*
            $(".menu").delay(400).queue(function(next) {
                $(this).css("z-index", "-1"); 
                next(); 
            });
            */

            $("#showSideMenu").removeClass("hidden");
            $("#goBackToHome").addClass("hidden");
            $("#songName").addClass("invisible");
        }

        function checkHeart(){
            $("#heartUncheck").addClass("hidden");
            $("#heartCheck").removeClass("hidden");
        }

        function uncheckHeart(){
            $("#heartCheck").addClass("hidden");
            $("#heartUncheck").removeClass("hidden");
        }

        $("#heartUncheck").on("click", function(){
            checkHeart();
        });

        $("#heartCheck").on("click", function(){
            uncheckHeart();
        });

        // Handle Audio

        var audioStatus = false;
        var audioStatus2 = false;
        var loopStatus = "loopOff";
        var repeatStatus = "repeatOff";

        $("#audioPlay").on("click", function(){
            handleAudio();
        });

        $("#audioPause").on("click", function(){
            handleAudio();
        });

        $("#audioLoop").on("click", function(){
            loopStatus = $("#loopStatus").attr("name");
            if(loopStatus == "loopOff"){
                $("#audioLoop").addClass("check-bottom-opt");
                $("#loopStatus").attr("name" , "loopOn");
                $(".inBack").attr("data-loop" , "1");
            } else if(loopStatus == "loopOn"){
                $("#audioLoop").removeClass("check-bottom-opt");
                $("#loopStatus").attr("name" , "loopOff");
                $(".inBack").attr("data-loop" , "0");
            }
        });

        $("#audioRepeat").on("click", function(){
            repeatStatus = $("#repeatStatus").attr("name");
            if(repeatStatus == "repeatOff"){
                $("#audioRepeat").addClass("check-bottom-opt");
                $("#repeatStatus").attr("name" , "repeatOn");
                $(".inBack").attr("data-autoplay" , "1");
            } else if(repeatStatus == "repeatOn"){
                $("#audioRepeat").removeClass("check-bottom-opt");
                $("#repeatStatus").attr("name" , "repeatOff");
                $(".inBack").attr("data-autoplay" , "0");
            }
        });

        $("#musicImage").on("click", function(){
            
            if(audioEl.paused && audioEl.currentTime > 0 && !audioEl.ended) {
                $("#audioPlay2").click();
            } else {
                $("#audioPause2").click();
            }
            $(".music-disk-con").animate({
                opacity: 0.2
            }, 100).animate({
                opacity: 1
            }, 100);
        });

        // $("[id^='btnCircleHandle_']").on("dblclick", function(){
        //     checkHeart();
        // });

        function handleAudio(){
            $("#audioHandler1").removeClass("hidden");
            $("#audioHandler2").addClass("hidden");
            if(audioStatus == false){
                $(".inBack").click();
                audioStatus = true;
                $("#audioPlay").addClass("hidden");
                $("#audioPause").removeClass("hidden");
            } else if(audioStatus == true){
                $(".inBack").click();
                audioStatus = false;
                $("#audioPlay").removeClass("hidden");
                $("#audioPause").addClass("hidden");
            } else {

            }
        }

        // Audio2

        function playAudio() { 
            audioEl.play(); 
        } 
        
        function pauseAudio() { 
            audioEl.pause(); 
        } 

        function handleAudio2(){
            
            $("#audioHandler2").removeClass("hidden");
            $("#audioHandler1").addClass("hidden");

        }

        $("#audioPlay2").on("click", function(){
            audioEl.play();
            $("#audioPlay2").addClass("hidden");
            $("#audioPause2").removeClass("hidden");

        });

        $("#audioPause2").on("click", function(){
            pauseAudio();
            $("#audioPlay2").removeClass("hidden");
            $("#audioPause2").addClass("hidden");
        });

        // playMusic({songImage: '', songName: '', songArtist: '', songID: ''});

        function playMusic(arg) {

            $("#hideOnMusic").addClass("invisible");

            $("#musicImage").css(
                "background", "url(" + arg.songImage + ")",
                "background-position", "center",
                "background-repeat", "no-repeat",
                "background-size", "cover"
            );

            $("#musicName").text(arg.songName);
            $("#songName2").text(arg.songName);
            $("#songName2").removeClass("invisible");
            $("#musicArtist").text(arg.songArtist);

            $("#audioElSource").attr("src", arg.songID);
            document.getElementById("audioEl").load();

            showMusic();
            handleAudio2();
            $("#audioPlay2").click();

            $("#musicImage").animate({
                opacity: 0.2
            }, 600, function(){
                $("#musicImage").animate({
                    opacity: 1
                }, 600, function(){
                    $("#musicImage").animate({
                        opacity: 0.2
                    }, 600, function(){
                        $("#musicImage").animate({
                            opacity: 1
                        }, 600 , function(){
                            // $("#musicImage").animate({
                            //     opacity: 0.2
                            // }, 600 , function(){
                            //     $("#musicImage").animate({
                            //         opacity: 1
                            //     }, 600 , function(){
                            //         $("#musicImage").animate({
                            //             opacity: 0.2
                            //         }, 600 , function(){
                            //             $("#musicImage").animate({
                            //                 opacity: 1
                            //             }, 600 , function(){
                                            
                            //             });
                            //         });
                            //     });
                            // });
                        });
                    });
                });
            });

        }

        // Splash Screen

        $('#zTwo').delay(800).queue(function (next) { 
            $(this).css('transform', 'rotate(90deg)'); 
            next(); 
        });

        $('#splashScreen').delay(1800).queue(function (next) { 
            $(this).css(
                "top", "-100vh"
            ); 
            $(this).css(
                "opacity", "0.6"
            );
            next(); 
        });
    </script>
</body>
</html>
