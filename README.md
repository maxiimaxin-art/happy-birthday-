<!DOCTYPE html>
[index.html](https://github.com/user-attachments/files/34522094/index.html)

<html lang="en">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<title>For You</title>
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@1,500;1,600&family=DM+Sans:wght@400&display=swap" rel="stylesheet">
<style>
:root{--bg:#ffeef3;--bg2:#ffffff;--rose:#ff5d8a;--gold:#d6336c;--text:#5a1f3a;
 box-sizing:border-box;padding-top:env(safe-area-inset-top,0px);padding-bottom:env(safe-area-inset-bottom,0px)}
*,*::before,*::after{box-sizing:inherit}
html,body{height:100%;margin:0}
html{color-scheme:light;scroll-padding-top:env(safe-area-inset-top,0px)}
body{background:radial-gradient(ellipse at 50% 40%,var(--bg2),var(--bg) 75%);color:var(--text);font-family:'DM Sans',system-ui,sans-serif;overflow:hidden;touch-action:none;user-select:none;-webkit-user-select:none}
.stars{position:fixed;inset:0;pointer-events:none}
.stars i{position:absolute;font-style:normal;line-height:1;color:#ff8fb0;opacity:.5;animation:tw 4s ease-in-out infinite}
@keyframes tw{50%{opacity:.1}}
#heart{position:fixed;left:50%;top:44%;width:min(54vw,230px);aspect-ratio:1;transform:translate(-50%,-50%)}
#heart .in{width:100%;height:100%;animation:float 3.2s ease-in-out infinite;filter:drop-shadow(0 0 28px rgba(255,100,150,.55))}
#heart svg{width:100%;height:100%;overflow:visible}
@keyframes float{50%{transform:translateY(-10px) scale(1.03)}}
#heart.pop .in{animation:pop .35s ease-out forwards}
@keyframes pop{40%{transform:scale(1.3)}100%{transform:scale(1.7);opacity:0}}
.ring{position:fixed;border:3px solid var(--rose);border-radius:50%;width:40px;height:40px;transform:translate(-50%,-50%);opacity:.9;animation:ring .9s ease-out forwards;pointer-events:none}
@keyframes ring{to{width:420px;height:420px;opacity:0}}
#bow{position:fixed;left:30px;bottom:calc(18px + env(safe-area-inset-bottom,0px));width:150px;height:206px;pointer-events:none}
#bow svg{width:100%;height:100%;overflow:visible}
#str{position:fixed;inset:0;width:100%;height:100%;pointer-events:none}
#arrow{position:fixed;width:140px;height:44px;cursor:grab;touch-action:none;z-index:5}
#arrow.back{transition:left .45s cubic-bezier(.3,1.4,.5,1),top .45s cubic-bezier(.3,1.4,.5,1),transform .45s}
#arrow.drag{cursor:grabbing}
#arrow.gone{opacity:0;transition:opacity .25s;pointer-events:none}
#arrow svg{width:100%;height:100%;display:block;filter:drop-shadow(0 0 5px rgba(214,51,108,.35))}
#arrow:focus-visible{outline:2px solid var(--gold)}
#hint{position:fixed;left:0;right:0;top:calc(env(safe-area-inset-top,0px) + 6vh);max-width:560px;margin:0 auto;text-align:center;opacity:.9;font-family:'Cormorant Garamond',Georgia,serif;font-style:italic;font-weight:600;font-size:clamp(1.3rem,5.5vw,1.8rem);color:var(--gold);padding:0 20px;text-shadow:0 1px 10px rgba(255,255,255,.95);transition:opacity .5s;pointer-events:none}
.b{position:fixed;pointer-events:none;z-index:4}
.b svg{width:100%;height:100%;overflow:visible}
.w{transform-origin:20px 15px;animation:flap .22s ease-in-out infinite alternate}
@keyframes flap{to{transform:scaleX(.3)}}
#msg{position:fixed;inset:0;display:flex;flex-direction:column;align-items:center;justify-content:center;text-align:center;padding:24px;pointer-events:none}
#msg p{margin:0;font-family:'Cormorant Garamond',Georgia,serif;font-style:italic;font-weight:600;color:var(--gold);text-shadow:0 2px 14px rgba(255,255,255,.95);line-height:1.15}
#msg .l1{font-size:clamp(2.6rem,12vw,5rem)}
#msg .l2{font-size:clamp(1.7rem,7.5vw,3rem);margin-top:10px;color:var(--text)}
#msg .l3{font-size:clamp(3.4rem,17vw,6.5rem);margin-top:4px}
#msg span{display:inline-block;opacity:0;transform:translateY(14px);transition:opacity 1s,transform 1s;margin:0 .14em}
#msg.show span{opacity:1;transform:none}
.fh{position:fixed;left:0;top:0;z-index:8;pointer-events:none;line-height:1;will-change:transform}
#p2{position:fixed;inset:0;z-index:6;overflow-y:auto;overflow-x:hidden;-webkit-overflow-scrolling:touch;touch-action:pan-y;text-align:center;opacity:0;transform:translateY(-100%);transition:opacity 1.2s,transform 1.4s cubic-bezier(.2,.8,.2,1);pointer-events:none}
#p2.show{opacity:1;transform:none;pointer-events:auto}
#p2 h2{margin:0 0 14px;font:italic 600 clamp(2.4rem,11vw,4.2rem)/1.1 'Cormorant Garamond',Georgia,serif;color:var(--gold);text-shadow:0 2px 14px rgba(255,255,255,.95)}
#p2 p{margin:0 auto;max-width:30ch;font:italic 500 clamp(1.3rem,5.5vw,1.9rem)/1.35 'Cormorant Garamond',Georgia,serif;color:var(--text);text-shadow:0 2px 12px rgba(255,255,255,.95)}
.go #msg,.go #bow,.go #str,.go #hint,.go #heart{opacity:0!important;transition:opacity .8s}
.p2h{padding:calc(env(safe-area-inset-top,0px) + 8vh) 20px 26px}
.dn{color:var(--rose);font-size:1.8rem;margin-top:10px;animation:bob 1.6s ease-in-out infinite}
@keyframes bob{50%{transform:translateY(8px)}}
#chain{position:relative;max-width:520px;margin:0 auto}
.br{position:absolute;left:50%;top:0;margin-left:-40px}
.item{position:absolute;left:0;right:0;height:300px}
.twig{position:absolute;top:0;height:20px;width:calc(16px + min(21vw,90px));z-index:2}
.twig svg{width:100%;height:100%;display:block;overflow:visible}
.R .twig svg{transform:scaleX(-1)}
.twig::after{content:'';position:absolute;top:9px;width:10px;height:10px;border-radius:50%;background:#ff8fb0}
.L .twig{right:50%}.L .twig::after{left:-4px}
.R .twig{left:50%}.R .twig::after{right:-4px}
.pol{position:absolute;top:34px;width:min(42vw,180px);background:#fff;padding:8px 8px 6px;box-shadow:0 8px 20px rgba(120,40,70,.25);transform-origin:50% -20px;transform:rotate(var(--r));opacity:0;z-index:3;text-align:center}
.pol::before{content:'';position:absolute;left:50%;top:-20px;height:20px;width:1.5px;background:#8a5a3c}
.L .pol{right:calc(50% + 16px)}.R .pol{left:calc(50% + 16px)}
.pol.in{animation:drop 1.3s ease-out forwards}
@keyframes drop{0%{opacity:0;transform:translateY(-70px) rotate(calc(var(--r) + 14deg))}40%{opacity:1;transform:rotate(calc(var(--r) - 8deg))}70%{transform:rotate(calc(var(--r) + 4deg))}100%{opacity:1;transform:rotate(var(--r))}}
.ph{aspect-ratio:1;background:linear-gradient(135deg,#ffd6e3,#ffeef3);display:flex;align-items:center;justify-content:center;font-size:44px;color:#ff8fb0;overflow:hidden}
.ph img{width:100%;height:100%;object-fit:cover;display:block}
.cap{font:italic 600 1.1rem 'Cormorant Garamond',Georgia,serif;color:var(--text);padding:8px 2px 4px;line-height:1.1}
.fl{position:absolute;z-index:2;line-height:0;transform:scale(0);transition:transform .7s cubic-bezier(.3,1.5,.5,1)}
.lf{position:absolute;z-index:2;width:16px;height:8px;border-radius:80% 0 80% 0;background:#7bb77a;transform:rotate(var(--lr)) scale(0);transition:transform .6s}
.fl.in{transform:scale(1)}.lf.in{transform:rotate(var(--lr)) scale(1)}
.story{position:absolute;top:34px;font:italic 500 1.02rem/1.35 'Cormorant Garamond',Georgia,serif;color:var(--text);text-align:left;text-shadow:0 1px 8px rgba(255,255,255,.95);opacity:0;transform:translateY(10px);transition:opacity .9s .5s,transform .9s .5s;z-index:3}
.story.in{opacity:1;transform:none}
.L .story{left:calc(50% + 40px);right:8px}
.R .story{right:calc(50% + 40px);left:8px}
#p2 .end{margin:24px auto 0;padding:0 20px}
#p2 .tap{font-size:1rem;opacity:.75;margin-top:16px}
#hb{display:block;margin:6px auto calc(14vh + env(safe-area-inset-bottom,0px));background:none;border:0;padding:8px 14px;font-size:54px;line-height:1;color:#ff5d8a;cursor:pointer;filter:drop-shadow(0 4px 10px rgba(255,93,138,.4));animation:hop 1s ease-in-out infinite}
@keyframes hop{0%,100%{transform:translateY(0) scale(1.06,.9)}50%{transform:translateY(-24px) scale(.94,1.1)}}
#hb:focus-visible{outline:2px solid var(--gold);border-radius:14px}
.bh{position:fixed;left:0;top:0;width:100px;height:90px;z-index:9;pointer-events:none;filter:drop-shadow(0 0 30px rgba(255,100,150,.6))}
.bh svg{width:100%;height:100%;display:block}
.flash{position:fixed;inset:0;z-index:9;pointer-events:none;background:radial-gradient(circle at 50% 50%,#fff,rgba(255,200,220,.7) 50%,transparent 78%);opacity:0;animation:fl .8s ease-out forwards}
@keyframes fl{15%{opacity:1}100%{opacity:0}}
#p3,#p4,#p5,#p6{position:fixed;inset:0;z-index:6;display:flex;flex-direction:column;align-items:center;justify-content:center;text-align:center;padding:24px;opacity:0;transition:opacity 1.4s;pointer-events:none}
#p3.show,#p4.show,#p5.show,#p6.show{opacity:1;pointer-events:auto}
#p3 h2,#p4 h2{margin:0 0 14px;font:italic 600 clamp(2.4rem,11vw,4.2rem)/1.1 'Cormorant Garamond',Georgia,serif;color:var(--gold);text-shadow:0 2px 14px rgba(255,255,255,.95)}
#p3 p,#p4 p{margin:0 auto;max-width:30ch;font:italic 500 clamp(1.3rem,5.5vw,1.9rem)/1.35 'Cormorant Garamond',Georgia,serif;color:var(--text);text-shadow:0 2px 12px rgba(255,255,255,.95)}
.sp{position:relative;background:#fff;border:2.5px solid #ff8fb0;border-radius:22px;padding:14px 24px;margin-bottom:22px;text-align:center;font:italic 600 clamp(1.7rem,8vw,2.4rem)/1.15 'Cormorant Garamond',Georgia,serif;color:var(--gold);box-shadow:0 10px 26px rgba(214,51,108,.22);animation:rise .7s .5s ease-out both}
.sp::after{content:'';position:absolute;left:50%;bottom:-12px;width:20px;height:20px;background:#fff;border-right:2.5px solid #ff8fb0;border-bottom:2.5px solid #ff8fb0;transform:translateX(-50%) rotate(45deg)}
#bear{width:min(56vw,220px);height:auto;overflow:visible;transform-origin:50% 100%;animation:enter .9s cubic-bezier(.3,1.5,.5,1) both,sway 2.6s ease-in-out .9s infinite}
@keyframes enter{from{transform:translateY(60px) scale(.7);opacity:0}}
@keyframes sway{0%,100%{transform:rotate(-2.2deg)}50%{transform:rotate(2.2deg)}}
.fw{transform-box:fill-box;transform-origin:50% 100%;animation:fsw 1.6s ease-in-out infinite alternate}
@keyframes fsw{from{transform:rotate(-7deg)}to{transform:rotate(7deg)}}
.eyes{transform-box:fill-box;transform-origin:50% 50%;animation:blink 4s infinite}
@keyframes blink{0%,94%,100%{transform:scaleY(1)}97%{transform:scaleY(.1)}}
#bear.happy{animation:jump .6s ease-in-out infinite}
@keyframes jump{50%{transform:translateY(-26px) scale(1.04)}}
.row{display:flex;gap:14px;flex-wrap:wrap;justify-content:center;margin-top:24px;transition:opacity .5s}
.ob{padding:13px 26px;border-radius:999px;font:500 1.05rem 'DM Sans',system-ui,sans-serif;cursor:pointer;border:2px solid #ff5d8a;opacity:0;animation:rise .7s ease-out forwards;touch-action:manipulation}
#yes{background:#ff5d8a;color:#fff;animation-delay:1.3s}
#no{background:#fff;color:#d6336c;animation-delay:1.6s}
@keyframes rise{from{opacity:0;transform:translateY(24px)}to{opacity:1;transform:none}}
.bhint{opacity:0;margin-top:18px;font:italic 600 1.4rem 'Cormorant Garamond',Georgia,serif;color:var(--gold);transition:opacity .8s;pointer-events:none}
#bear.happy{cursor:pointer}
#p4{--w:min(86vw,420px);padding:20px 16px}
.env2{position:relative;width:var(--w);height:calc(var(--w)*.68);flex:none;transition:opacity .9s,transform .9s;filter:drop-shadow(0 24px 40px rgba(120,80,10,.45))}
.env2.gone{opacity:0;transform:scale(.88) translateY(40px);pointer-events:none}
.e-back,.e-front{position:absolute;inset:0;border-radius:10px;background:repeating-linear-gradient(45deg,rgba(255,255,255,.1) 0 2px,transparent 2px 12px),repeating-linear-gradient(-45deg,rgba(110,60,0,.09) 0 2px,transparent 2px 12px),linear-gradient(135deg,#fbe9a0,#d9a63b 40%,#9a6a12 68%,#f6d870)}
.e-front{z-index:3;background-image:repeating-linear-gradient(45deg,rgba(255,255,255,.1) 0 2px,transparent 2px 12px),repeating-linear-gradient(-45deg,rgba(110,60,0,.09) 0 2px,transparent 2px 12px),linear-gradient(160deg,#f7da6c,#c99128 60%,#a87414);clip-path:polygon(0 0,50% 56%,100% 0,100% 100%,0 100%)}
.fr{position:absolute;z-index:3;pointer-events:none;border-radius:6px}
.f1{inset:2.2%;border:5px double #fff4c6;box-shadow:inset 0 0 0 1px #9c6b12,0 0 0 1px #9c6b12}
.f2{inset:4.8%;border:2px solid #7a4f0c}
.f3{inset:6.8%;border:4px dotted #fff8dc}
.e-from{position:absolute;left:0;right:0;bottom:8%;z-index:4;text-align:center;font:italic 600 clamp(1rem,4.6vw,1.35rem) 'Cormorant Garamond',Georgia,serif;color:#5a3a06;text-shadow:0 1px 0 rgba(255,240,180,.8)}
.e-from::before,.e-from::after{content:'';display:inline-block;width:14%;height:2px;vertical-align:middle;margin:0 10px;background:linear-gradient(90deg,transparent,#7a4f0c)}
.e-from::after{background:linear-gradient(270deg,transparent,#7a4f0c)}
.e-flap{position:absolute;left:0;right:0;top:0;height:56%;z-index:4;background:linear-gradient(180deg,#fbe48e,#d9a63b);clip-path:polygon(0 0,100% 0,50% 100%);transform-origin:top;transition:transform .7s ease,z-index 0s .35s}
.e-lin{position:absolute;inset:0;z-index:1;border-radius:10px;clip-path:polygon(0 0,50% 56%,100% 0);background:repeating-radial-gradient(circle,rgba(255,215,130,.14) 0 2px,transparent 2px 9px),radial-gradient(circle at 50% 0,#a02a42,#6e1022 70%)}
.e-lin2{position:absolute;left:0;right:0;top:-56%;height:56%;z-index:1;clip-path:polygon(2% 98%,98% 98%,50% 6%);background:repeating-radial-gradient(circle,rgba(255,215,130,.14) 0 2px,transparent 2px 9px),linear-gradient(0deg,#8f1d35,#5e0d1f);opacity:0;transition:opacity .3s .4s}
.env2.open .e-lin2{opacity:1}
.e-flap::before,.e-flap::after{content:'';position:absolute;inset:0}
.e-flap::before{background:linear-gradient(180deg,#f2d06a,#bf8420);clip-path:polygon(4% 3%,96% 3%,50% 90%)}
.e-flap::after{background:linear-gradient(180deg,#fff0b3,#e3b845);clip-path:polygon(9% 7%,91% 7%,50% 82%)}
.orn{position:absolute;z-index:6;width:clamp(30px,9vw,50px);pointer-events:none}
.orn svg{width:100%;display:block}
.orn.tl{left:2.6%;top:2.2%}.orn.tr{right:2.6%;top:2.2%;transform:scaleX(-1)}
.orn.bl{left:2.6%;bottom:2.2%;transform:scaleY(-1)}.orn.br{right:2.6%;bottom:2.2%;transform:scale(-1)}
.e-seal{--s:clamp(58px,17vw,76px);position:absolute;left:50%;top:56%;width:var(--s);height:var(--s);margin:calc(var(--s)/-2) 0 0 calc(var(--s)/-2);z-index:7;border-radius:50%;border:5px double #ffe9a0;background:radial-gradient(circle at 35% 30%,#f0506f,#b3203f 58%,#6e0f24);color:#ffe9a8;font-size:clamp(24px,7vw,34px);cursor:pointer;box-shadow:0 6px 16px rgba(0,0,0,.45),inset 0 0 0 4px rgba(120,10,30,.5);animation:beat2 2s ease-in-out infinite;transition:opacity .4s}
.e-seal::before{content:'';position:absolute;inset:5px;border-radius:50%;border:2px dotted #ffd980;pointer-events:none}
@keyframes beat2{50%{transform:scale(1.1)}}
.e-seal:focus-visible{outline:3px solid #fff;outline-offset:3px}
.env2.open .e-flap{transform:rotateX(180deg);z-index:1}
.env2.open .e-seal,.env2.open .ehint{opacity:0;pointer-events:none}
.ehint{position:absolute;left:0;right:0;top:calc(56% + 46px);z-index:7;text-align:center;font:italic 600 clamp(1rem,4.4vw,1.25rem) 'Cormorant Garamond',Georgia,serif;color:#5a3a06;text-shadow:0 1px 0 rgba(255,240,180,.8);transition:opacity .4s}
.gl{position:absolute;z-index:6;color:#fffbe0;text-shadow:0 0 8px #fff,0 0 14px #ffd86a;pointer-events:none;opacity:0;animation:tw2 2.4s ease-in-out infinite}
@keyframes tw2{50%{opacity:1;transform:scale(1.25) rotate(20deg)}}
.scroll{position:absolute;left:50%;top:50%;transform:translate(-50%,-50%);width:var(--w);display:flex;flex-direction:column;align-items:center;opacity:0;pointer-events:none;transition:opacity .6s;z-index:5}
.opened .scroll{opacity:1;pointer-events:auto}
.rod{position:relative;flex:none;width:calc(100% + 18px);height:20px;border-radius:10px;background:linear-gradient(#f9e79a,#c48a24 55%,#8f6410);box-shadow:0 4px 8px rgba(80,50,0,.35)}
.rod::before,.rod::after{content:'';position:absolute;top:-3px;width:14px;height:26px;border-radius:7px;background:radial-gradient(circle at 35% 30%,#fff3bd,#c48a24 70%)}
.rod::before{left:-6px}.rod::after{right:-6px}
.parch{width:100%;max-height:0;overflow:hidden;padding:0 20px;background:linear-gradient(180deg,#f3e2b8,#f8ecd0 20%,#f3e2b8 80%,#e6cf9b);box-shadow:inset 0 0 40px rgba(150,100,20,.3);text-align:center;scrollbar-width:none;transition:max-height 1.8s cubic-bezier(.3,.7,.2,1) .4s,padding 1.8s .4s}
.parch::-webkit-scrollbar{display:none}
.opened .parch{max-height:calc(var(--w)*.68 - 40px);overflow-y:auto;padding:22px 20px}
.parch h3{margin:0 0 10px;font:italic 600 clamp(1.9rem,8.5vw,2.6rem)/1.1 'Cormorant Garamond',Georgia,serif;color:var(--gold)}
#p4 .parch p{margin:.6em auto;max-width:none;font:italic 500 1.3rem/1.4 'Cormorant Garamond',Georgia,serif;color:#4a2a1a;text-shadow:none}
.gbtn{padding:13px 28px;border:0;border-radius:999px;background:#ff5d8a;color:#fff;font:500 1.05rem 'DM Sans',system-ui,sans-serif;cursor:pointer;box-shadow:0 8px 20px rgba(214,51,108,.35)}
#toGifts{position:absolute;left:50%;bottom:calc(5vh + env(safe-area-inset-bottom,0px));transform:translateX(-50%) translateY(20px);opacity:0;pointer-events:none;transition:opacity .8s,transform .8s;z-index:7}
#toGifts.on{opacity:1;transform:translateX(-50%);pointer-events:auto}
.g5t{font:italic 600 clamp(2rem,9vw,3rem)/1.1 'Cormorant Garamond',Georgia,serif;color:var(--gold);text-shadow:0 2px 14px rgba(255,255,255,.95);text-align:center;margin-bottom:8px}
.g5s{font:italic 500 1.35rem/1.3 'Cormorant Garamond',Georgia,serif;color:var(--text);text-align:center;margin-bottom:34px;min-height:1.6em}
.gifts{display:flex;gap:3vw;justify-content:center;align-items:flex-end}
.gift{position:relative;width:min(27vw,130px);background:none;border:0;padding:0;cursor:pointer;animation:gdrop .9s cubic-bezier(.3,1.5,.5,1) both}
.gift:nth-child(2){animation-delay:.25s}.gift:nth-child(3){animation-delay:.5s}
@keyframes gdrop{from{transform:translateY(-120px);opacity:0}}
.gift svg{width:100%;display:block;overflow:visible;filter:drop-shadow(0 8px 10px rgba(150,40,80,.25))}
.gift.ready svg{animation:gbounce 1.2s ease-in-out infinite}
@keyframes gbounce{0%,100%{transform:translateY(0)}50%{transform:translateY(-12px)}}
.gift.locked{filter:grayscale(.85);opacity:.55}
.gift.locked::after{content:"\1F512";position:absolute;left:50%;top:40%;transform:translateX(-50%);font-size:1.6rem}
.lid{transform-box:fill-box;transform-origin:50% 100%;transition:transform .8s cubic-bezier(.3,1.4,.5,1)}
.gift.opening .lid,.gift.open .lid{transform:translateY(-38px) rotate(-14deg)}
.glow{opacity:0;transition:opacity .6s}
.gift.opening .glow,.gift.open .glow{opacity:.95}
.gn{display:block;margin-top:6px;font:italic 600 1.3rem 'Cormorant Garamond',Georgia,serif;color:var(--gold)}
.vidov{position:fixed;inset:0;z-index:30;background:rgba(30,12,40,.94);display:flex;align-items:center;justify-content:center;opacity:0;pointer-events:none;transition:opacity .6s}
.vidov.on{opacity:1;pointer-events:auto}
#gv{width:min(94vw,720px);max-height:82vh;border-radius:14px;background:#000}
.vplay{position:absolute;left:50%;top:50%;width:84px;height:84px;margin:-42px 0 0 -42px;border-radius:50%;border:0;background:#ff5d8a;color:#fff;font-size:34px;cursor:pointer;opacity:0;pointer-events:none}
.vplay.on{opacity:1;pointer-events:auto}
.vend{position:absolute;inset:0;display:flex;flex-direction:column;align-items:center;justify-content:center;gap:22px;background:rgba(30,12,40,.78);color:#fff;text-align:center;padding:24px;font:italic 600 clamp(1.9rem,8vw,2.8rem)/1.2 'Cormorant Garamond',Georgia,serif;opacity:0;pointer-events:none;transition:opacity .6s}
.vend.on{opacity:1;pointer-events:auto}
.gift{width:min(40vw,170px)}
.gn{display:none}
.bal{position:fixed;left:50%;top:calc(6vh + env(safe-area-inset-top,0px));width:min(30vw,120px);margin-left:calc(min(30vw,120px)/-2);display:none;z-index:8;cursor:pointer;transform-origin:50% 100%}
.bal svg{width:100%;display:block;overflow:visible;filter:drop-shadow(0 8px 8px rgba(150,30,70,.25))}
.bal.float{animation:bsway 3s ease-in-out infinite}
@keyframes bsway{0%,100%{transform:translateY(0) rotate(-3deg)}50%{transform:translateY(-10px) rotate(3deg)}}
.gun{position:fixed;left:12px;bottom:calc(16px + env(safe-area-inset-bottom,0px));width:min(34vw,130px);display:none;z-index:8;cursor:pointer;transition:transform .5s}
.gun svg{width:100%;display:block;overflow:visible;filter:drop-shadow(0 6px 6px rgba(150,30,70,.3))}
.popt{position:fixed;left:0;top:0;z-index:11;pointer-events:none;font:italic 700 clamp(2.4rem,12vw,4rem) 'Cormorant Garamond',Georgia,serif;color:#ff3d78;text-shadow:0 2px 12px #fff,0 0 20px #fff}
.vidov{flex-direction:column}
#gv{max-height:74vh}
.vend{position:static;background:none;padding:0;margin-top:22px;gap:0;display:flex}
.b6t{position:fixed;left:50%;top:calc(6vh + env(safe-area-inset-top,0px));transform:translateX(-50%);width:min(90vw,520px);text-align:center;font:italic 600 clamp(1.5rem,6.6vw,2.2rem)/1.2 'Cormorant Garamond',Georgia,serif;color:var(--gold);text-shadow:0 2px 12px rgba(255,255,255,.95);z-index:8;transition:opacity .6s}
.bal6{position:fixed;top:25vh;width:min(34vw,140px);display:none;z-index:8;transform-origin:50% 100%}
.bal6 svg{width:100%;display:block;overflow:visible;filter:drop-shadow(0 8px 8px rgba(150,30,70,.25))}
.bal6.float{animation:bsway 3s ease-in-out infinite}
.gun6{position:fixed;bottom:calc(4vh + 40px + env(safe-area-inset-bottom,0px));width:min(34vw,130px);display:none;z-index:8;cursor:pointer;transform:rotate(-90deg)}
.gun6 svg{width:100%;display:block;overflow:visible;filter:drop-shadow(0 6px 6px rgba(150,30,70,.3))}
.g6h{position:fixed;left:0;right:0;bottom:calc(1.5vh + env(safe-area-inset-bottom,0px));text-align:center;font:italic 600 1.3rem 'Cormorant Garamond',Georgia,serif;color:var(--gold);text-shadow:0 2px 10px rgba(255,255,255,.95);z-index:8;opacity:0;transition:opacity .6s;pointer-events:none}
.stage6{position:fixed;inset:0;z-index:7;display:flex;flex-direction:column;align-items:center;justify-content:center;padding:24px;text-align:center;opacity:0;pointer-events:none;transition:opacity 1s}
.stage6.on{opacity:1;pointer-events:auto}
.sm{background:none;border:0;cursor:pointer;font:italic 600 clamp(2rem,9vw,3.2rem)/1.15 'Cormorant Garamond',Georgia,serif;color:var(--gold);text-shadow:0 2px 14px rgba(255,255,255,.95);max-width:min(90vw,520px);animation:smp 1.8s ease-in-out infinite}
.sm small{display:block;margin-top:14px;font:500 1rem 'DM Sans',system-ui,sans-serif;color:#d6336c}
@keyframes smp{50%{transform:scale(1.04)}}
.q6,.fin6{display:none}
.q6{flex-direction:column;align-items:center}
.q6t{font:italic 600 clamp(2.2rem,10vw,3.6rem)/1.1 'Cormorant Garamond',Georgia,serif;color:var(--gold);text-shadow:0 2px 14px rgba(255,255,255,.95);margin-bottom:26px}
.row6{display:flex;gap:16px;justify-content:center}
#y6{background:#ff5d8a;color:#fff;animation-delay:.3s}
#n6{background:#fff;color:#d6336c;animation-delay:.5s}
.q6s{margin-top:16px;min-height:1.6em;font:italic 600 1.3rem 'Cormorant Garamond',Georgia,serif;color:#d6336c}
.fin6{max-width:min(90vw,520px);font:italic 600 clamp(1.7rem,7.5vw,2.5rem)/1.3 'Cormorant Garamond',Georgia,serif;color:var(--gold);text-shadow:0 2px 14px rgba(255,255,255,.95)}
@media (prefers-reduced-motion:reduce){#heart .in,.stars i{animation:none}}
</style>
</head>
<body>
<div class="stars" id="stars" aria-hidden="true"></div>

<div id="heart" aria-hidden="true"><div class="in">
<svg viewBox="0 0 100 90"><defs>
<radialGradient id="g" cx="35%" cy="30%" r="80%"><stop offset="0" stop-color="#ffb3c9"/><stop offset=".5" stop-color="#ff5d8a"/><stop offset="1" stop-color="#b3123f"/></radialGradient></defs>
<path d="M50 86C8 56-2 30 14 14C29 0 46 8 50 22C54 8 71 0 86 14C102 30 92 56 50 86Z" fill="url(#g)" stroke="rgba(255,255,255,.55)" stroke-width="1.2"/>
<ellipse cx="30" cy="24" rx="10" ry="6" transform="rotate(-35 30 24)" fill="#fff" opacity=".55"/>
<circle cx="22" cy="38" r="2.2" fill="#fff" opacity=".5"/></svg></div></div>

<div id="bow" aria-hidden="true"><svg viewBox="0 0 160 220">
<defs><linearGradient id="wd" x1="0" y1="0" x2="1" y2="0"><stop offset="0" stop-color="#7a3b22"/><stop offset=".5" stop-color="#c47a3f"/><stop offset="1" stop-color="#8a4a28"/></linearGradient></defs>
<path d="M46 10C84 36 104 70 104 110C104 150 84 184 46 210" fill="none" stroke="#3a1a10" stroke-width="12" stroke-linecap="round"/>
<path d="M46 10C84 36 104 70 104 110C104 150 84 184 46 210" fill="none" stroke="url(#wd)" stroke-width="8.5" stroke-linecap="round"/>
<path d="M52 16C86 40 101 72 101 110" fill="none" stroke="#ffd9a3" stroke-opacity=".55" stroke-width="1.8" stroke-linecap="round"/>
<rect x="97" y="88" width="14" height="44" rx="6" fill="#4a1f2c" stroke="#ff7fa3" stroke-width="1.2"/>
<path d="M97 98H111M97 108H111M97 118H111" stroke="#ff7fa3" stroke-opacity=".6" stroke-width="1.2"/>
<circle cx="46" cy="10" r="5" fill="#e8b86b"/><circle cx="46" cy="210" r="5" fill="#e8b86b"/></svg></div>

<svg id="str" aria-hidden="true"><polyline id="strl" fill="none" stroke="#b04a6a" stroke-opacity=".9" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"/></svg>
<div id="arrow" role="button" tabindex="0" aria-label="Arrow. Pull it back and release to shoot the heart. Press Enter to shoot.">
<svg viewBox="0 0 140 44"><line x1="8" y1="22" x2="122" y2="22" stroke="#c98a4b" stroke-width="3.5" stroke-linecap="round"/>
<polygon points="139,22 117,11 117,33" fill="#ff7fa3"/>
<polyline points="6,22 0,13 15,13 24,22 15,31 0,31 6,22" fill="#ff7fa3"/>
<polyline points="22,22 16,16 28,16 34,22 28,28 16,28 22,22" fill="#e8b86b" opacity=".95"/></svg></div>

<p id="hint">Break my heart with your love arrow to see the magic</p>
<div id="msg" aria-live="polite">
<p class="l1"><span>Happy</span><span>birthday</span></p>
<p class="l2"><span>to</span><span>my</span><span>lovely</span><span>queen,</span></p>
<p class="l3"><span>Libia</span></p></div>
<div id="p2"><header class="p2h"><h2>Our story</h2><p>Every moment with you is my favourite chapter.</p><div class="dn" aria-hidden="true">&#8595;</div></header><div id="chain"></div><p class="end">And the best chapters are still to come &#9829;</p><p class="tap">Tap the little heart to continue</p><button id="hb" aria-label="Tap the heart to continue">&#9829;</button></div>
<div id="p3">
<div class="sp" id="sp">Do you love me?</div>
<svg id="bear" viewBox="0 0 220 260" aria-label="A cute brown teddy bear holding a flower">
<ellipse cx="110" cy="250" rx="62" ry="7" fill="rgba(90,40,60,.18)"/>
<ellipse cx="74" cy="230" rx="26" ry="18" fill="#8b5a3c"/><ellipse cx="146" cy="230" rx="26" ry="18" fill="#8b5a3c"/>
<ellipse cx="74" cy="234" rx="13" ry="9" fill="#d9a67a"/><ellipse cx="146" cy="234" rx="13" ry="9" fill="#d9a67a"/>
<ellipse cx="110" cy="180" rx="54" ry="58" fill="#a06a42"/><ellipse cx="110" cy="190" rx="34" ry="40" fill="#e8c39a"/>
<ellipse cx="58" cy="178" rx="15" ry="36" transform="rotate(18 58 178)" fill="#8b5a3c"/>
<circle cx="66" cy="46" r="24" fill="#8b5a3c"/><circle cx="66" cy="46" r="13" fill="#d9a67a"/>
<circle cx="154" cy="46" r="24" fill="#8b5a3c"/><circle cx="154" cy="46" r="13" fill="#d9a67a"/>
<circle cx="110" cy="88" r="54" fill="#a06a42"/>
<ellipse cx="110" cy="106" rx="26" ry="20" fill="#e8c39a"/>
<ellipse cx="80" cy="102" rx="9" ry="6" fill="#ff9db8" opacity=".6"/><ellipse cx="140" cy="102" rx="9" ry="6" fill="#ff9db8" opacity=".6"/>
<ellipse cx="110" cy="98" rx="8" ry="6" fill="#3b2218"/>
<path d="M110 104V110M110 110Q101 118 95 110M110 110Q119 118 125 110" fill="none" stroke="#3b2218" stroke-width="2.5" stroke-linecap="round"/>
<g class="eyes"><circle cx="90" cy="80" r="6.5" fill="#2a1810"/><circle cx="130" cy="80" r="6.5" fill="#2a1810"/><circle cx="92" cy="77.5" r="2.2" fill="#fff"/><circle cx="132" cy="77.5" r="2.2" fill="#fff"/></g>
<polygon points="110,148 90,136 90,160" fill="#ff5d8a"/><polygon points="110,148 130,136 130,160" fill="#ff5d8a"/><circle cx="110" cy="148" r="6" fill="#e63e78"/>
<ellipse cx="164" cy="160" rx="15" ry="36" transform="rotate(38 164 160)" fill="#8b5a3c"/>
<g class="fw"><path d="M186 130Q192 102 194 72" fill="none" stroke="#4f9a4f" stroke-width="5" stroke-linecap="round"/>
<ellipse cx="203" cy="100" rx="11" ry="5" transform="rotate(-35 203 100)" fill="#6cc070"/>
<g transform="translate(194 62)" fill="#ff6f9c" stroke="#e0507f" stroke-width="1.2"><ellipse cy="-12" rx="8" ry="12"/><ellipse cy="-12" rx="8" ry="12" transform="rotate(60)"/><ellipse cy="-12" rx="8" ry="12" transform="rotate(120)"/><ellipse cy="-12" rx="8" ry="12" transform="rotate(180)"/><ellipse cy="-12" rx="8" ry="12" transform="rotate(240)"/><ellipse cy="-12" rx="8" ry="12" transform="rotate(300)"/><circle r="7" fill="#ffd45e" stroke="none"/></g></g>
<circle cx="187" cy="130" r="13" fill="#8b5a3c"/></svg>
<div class="bhint" id="bhint">Tap the bear &#9829;</div>
<div class="row" id="row"><button class="ob" id="yes">Yes, I love you &#9829;</button><button class="ob" id="no">No</button></div>
</div>

<div id="p4">
<div class="env2" id="env2">
<div class="e-back"></div><div class="e-lin"></div><div class="e-front"></div>
<div class="fr f1"></div><div class="fr f2"></div><div class="fr f3"></div>
<div class="e-from">From me, to you &#9829;</div>
<div class="e-flap"></div><div class="e-lin2"></div>
<div class="orn tl"><svg viewBox="0 0 60 60"><path d="M4 56V22Q4 4 22 4H56" fill="none" stroke="#6b430a" stroke-width="3.2" stroke-linecap="round"/><path d="M11 50V25Q11 11 25 11H50" fill="none" stroke="#fff3bd" stroke-width="2" stroke-linecap="round"/><path d="M16 16Q34 18 30 34Q16 32 16 16Z" fill="#6b430a" opacity=".85"/><circle cx="9" cy="9" r="5" fill="#fff3bd" stroke="#6b430a" stroke-width="2"/></svg></div><div class="orn tr"><svg viewBox="0 0 60 60"><path d="M4 56V22Q4 4 22 4H56" fill="none" stroke="#6b430a" stroke-width="3.2" stroke-linecap="round"/><path d="M11 50V25Q11 11 25 11H50" fill="none" stroke="#fff3bd" stroke-width="2" stroke-linecap="round"/><path d="M16 16Q34 18 30 34Q16 32 16 16Z" fill="#6b430a" opacity=".85"/><circle cx="9" cy="9" r="5" fill="#fff3bd" stroke="#6b430a" stroke-width="2"/></svg></div><div class="orn bl"><svg viewBox="0 0 60 60"><path d="M4 56V22Q4 4 22 4H56" fill="none" stroke="#6b430a" stroke-width="3.2" stroke-linecap="round"/><path d="M11 50V25Q11 11 25 11H50" fill="none" stroke="#fff3bd" stroke-width="2" stroke-linecap="round"/><path d="M16 16Q34 18 30 34Q16 32 16 16Z" fill="#6b430a" opacity=".85"/><circle cx="9" cy="9" r="5" fill="#fff3bd" stroke="#6b430a" stroke-width="2"/></svg></div><div class="orn br"><svg viewBox="0 0 60 60"><path d="M4 56V22Q4 4 22 4H56" fill="none" stroke="#6b430a" stroke-width="3.2" stroke-linecap="round"/><path d="M11 50V25Q11 11 25 11H50" fill="none" stroke="#fff3bd" stroke-width="2" stroke-linecap="round"/><path d="M16 16Q34 18 30 34Q16 32 16 16Z" fill="#6b430a" opacity=".85"/><circle cx="9" cy="9" r="5" fill="#fff3bd" stroke="#6b430a" stroke-width="2"/></svg></div>
<button class="e-seal" id="seal" aria-label="Open the golden envelope">&#9829;</button>
<div class="ehint" id="ehint">Tap the golden seal to open &#9829;</div>
</div>
<button class="gbtn" id="toGifts">Your gifts are waiting &#9829;</button>
<div class="scroll" id="scroll"><div class="rod"></div>
<div class="parch"><h3>Hear my words for you.</h3><div id="lt"></div></div>
<div class="rod"></div></div>
</div>
<div id="p5">
<div class="g5t" id="g5t">A gift for you &#9829;</div>
<div class="g5s" id="g5s">Tap the gift</div>
<div class="gifts" id="gifts"></div>
</div>
<div id="p6">
<div class="b6t" id="b6t">Hey Libia, here you have an expensive proposal from your soulmate.</div>
<div class="bal6" id="bal6"></div>
<div class="gun6" id="gun6" role="button" tabindex="0" aria-label="Tap the gun to shoot the balloon"></div>
<div class="g6h" id="g6h">Tap the gun &#9829;</div>
<div class="stage6" id="stage6">
<button class="sm" id="sm">Hey gorgeous, this is your soulmate.<small>tap here &#9829;</small></button>
<div class="q6" id="q6"><div class="q6t">Will you marry me?</div><div class="row6"><button class="ob" id="y6">Yes</button><button class="ob" id="n6">No</button></div><div class="q6s" id="q6s"></div></div>
<div class="fin6" id="fin6">Congratulations, you are going to get married soon, and once again wish you many many happy returns of the day, my dear love. &#9829;</div>
</div>
</div>
<div class="vidov" id="vidov">
<video id="gv" playsinline preload="auto"></video>
<button class="vplay" id="vplay" aria-label="Play the video">&#9654;</button>
<div class="vend" id="vend"><button class="gbtn" id="vnext">Tap here &#9829;</button></div>
</div>
<script>
var $=function(i){return document.getElementById(i)};
var p2=$('p2');
var heart=$('heart'),arrow=$('arrow'),bow=$('bow'),hint=$('hint'),msg=$('msg');
var flying=false,ready=false,going=false,pull=0,grab=null,tipA={x:0,y:0},tipB={x:0,y:0},HR=0,HC={x:0,y:0},rest={x:0,y:0,a:0},done=false,dragging=false,off={x:0,y:0};
for(var i=0;i<40;i++){var d=document.createElement('i');d.textContent='\u2665';d.style.fontSize=(8+Math.random()*14)+'px';d.style.left=Math.random()*100+'%';d.style.top=Math.random()*100+'%';d.style.animationDelay=Math.random()*4+'s';$('stars').appendChild(d)}

function drawString(nx,ny){$('strl').setAttribute('points',tipA.x+','+tipA.y+' '+nx+','+ny+' '+tipB.x+','+tipB.y)}
function place(x,y,a,noStr){arrow.style.left=(x-70)+'px';arrow.style.top=(y-22)+'px';arrow.style.transform='rotate('+a+'rad)';if(!noStr)drawString(x-Math.cos(a)*68,y-Math.sin(a)*68)}
function layout(){
  var r=heart.getBoundingClientRect();HC={x:r.left+r.width/2,y:r.top+r.height/2};HR=r.width/2;
  var bw=Math.min(150,innerWidth*.36),k=bw/160;
  bow.style.width=bw+'px';bow.style.height=(bw*220/160)+'px';bow.style.left=(18+20*k)+'px';
  var b=bow.getBoundingClientRect(),c={x:b.left+b.width/2,y:b.top+b.height/2};
  var a=Math.atan2(HC.y-c.y,HC.x-c.x),co=Math.cos(a),si=Math.sin(a);
  bow.style.transform='rotate('+a+'rad)';
  var sx=c.x-34*k*co,sy=c.y-34*k*si;
  rest={x:sx+co*68,y:sy+si*68,a:a};
  tipA={x:sx+100*k*si,y:sy-100*k*co};tipB={x:sx-100*k*si,y:sy+100*k*co};
  if(!dragging&&!done&&!flying)place(rest.x,rest.y,rest.a);
}
window.addEventListener('resize',layout);layout();
// fonts/viewport settle
setTimeout(layout,300);

arrow.addEventListener('pointerdown',function(e){
  if(done||flying)return;dragging=true;arrow.classList.remove('back');arrow.classList.add('drag');
  arrow.setPointerCapture(e.pointerId);grab={x:e.clientX,y:e.clientY};hint.style.opacity=0;e.preventDefault();
});
arrow.addEventListener('pointermove',function(e){
  if(!dragging||done||flying)return;
  var dx=e.clientX-grab.x,dy=e.clientY-grab.y,cx=Math.cos(rest.a),cy=Math.sin(rest.a);
  pull=Math.max(0,Math.min(80,-(dx*cx+dy*cy)));
  place(rest.x-cx*pull,rest.y-cy*pull,rest.a);
});
function release(){
  if(!dragging||done||flying)return;dragging=false;arrow.classList.remove('drag');
  if(pull>18){launch(pull)}else{arrow.classList.add('back');place(rest.x,rest.y,rest.a);hint.style.opacity=.9}
  pull=0;
}
function launch(p){
  if(flying||done)return;flying=true;dragging=false;hint.style.opacity=0;
  arrow.classList.remove('back','drag');
  var cx=Math.cos(rest.a),cy=Math.sin(rest.a),sx=rest.x-cx*p,sy=rest.y-cy*p;
  var ex=HC.x-cx*(70-HR*.25),ey=HC.y-cy*(70-HR*.25);
  drawString(rest.x-cx*68,rest.y-cy*68);
  var dur=300-p,t0=null;
  function step(t){
    if(t0===null)t0=t;var k=Math.min(1,(t-t0)/dur);k=k*k;
    place(sx+(ex-sx)*k,sy+(ey-sy)*k,rest.a,true);
    if(k<1)requestAnimationFrame(step);else burst();
  }
  requestAnimationFrame(step);
}
arrow.addEventListener('pointerup',release);arrow.addEventListener('pointercancel',release);
arrow.addEventListener('keydown',function(e){if(e.key==='Enter'||e.key===' '){e.preventDefault();launch(60)}});

var COLORS=['#ff7fa3','#e8a33d','#a67cff','#4fb3e8','#ff8a4c','#e63e78'];
function butterfly(col){
  var wing='<path d="M20 15C10-3 0 2 2 12C3 20 12 20 20 15Z"/><path d="M20 15C12 18 6 29 12 29C18 29 20 21 20 15Z" opacity=".85"/>';
  return '<svg viewBox="0 0 40 30" fill="'+col+'"><g class="w">'+wing+'</g><g transform="translate(40,0) scale(-1,1)"><g class="w">'+wing+'</g></g><ellipse cx="20" cy="15" rx="1.6" ry="8" fill="#2a1030"/></svg>';
}
function burst(){
  if(done)return;done=true;dragging=false;
  playSong();
  arrow.classList.remove('drag');arrow.classList.add('gone');
  heart.classList.add('pop');hint.style.opacity=0;
  var ring=document.createElement('div');ring.className='ring';ring.style.left=HC.x+'px';ring.style.top=HC.y+'px';document.body.appendChild(ring);
  setTimeout(function(){ring.remove()},1000);
  var W=innerWidth,H=innerHeight;
  for(var i=0;i<34;i++){(function(){
    var s=26+Math.random()*30,el=document.createElement('div');
    el.className='b';el.style.width=s+'px';el.style.height=s*.75+'px';el.style.left=HC.x+'px';el.style.top=HC.y+'px';
    el.innerHTML=butterfly(COLORS[Math.floor(Math.random()*COLORS.length)]);
    document.body.appendChild(el);
    function pt(){return{x:(Math.random()*1.2-.1)*W-HC.x,y:(Math.random()*1.2-.1)*H-HC.y}}
    var p1=pt(),p2=pt(),p3=pt();
    var T='translate(-50%,-50%) translate(';
    var anim=el.animate([
      {transform:T+'0px,0px) scale(.2) rotate(0deg)',opacity:0},
      {transform:T+p1.x+'px,'+p1.y+'px) scale(1) rotate('+(Math.random()*40-20)+'deg)',opacity:1,offset:.25},
      {transform:T+p2.x+'px,'+p2.y+'px) scale(1) rotate('+(Math.random()*40-20)+'deg)',opacity:1,offset:.65},
      {transform:T+p3.x+'px,'+p3.y+'px) scale(.7) rotate('+(Math.random()*40-20)+'deg)',opacity:0}
    ],{duration:5500+Math.random()*3500,delay:Math.random()*500,easing:'ease-in-out',fill:'forwards'});
    anim.onfinish=function(){el.remove()};
  })()}
  setTimeout(function(){msg.classList.add('show');
    var sp=msg.querySelectorAll('span');
    for(var k=0;k<sp.length;k++)sp[k].style.transitionDelay=(k*0.35)+'s';
  },2200);
  setTimeout(function(){ready=true;hint.textContent='Tap anywhere to continue \u2665';hint.style.opacity=.9},6200);
}
// ================= PHOTO SPACES (PAGE 2) =================
// GITHUB: make a folder called  photos  in your repository and upload your 6 photos with these names:
//   photo1.jpg, photo2.jpg, photo3.jpg, photo4.jpg, photo5.jpg, photo6.jpg   (lowercase, no spaces, .jpg)
// If a photo is missing, that frame just shows the pink heart.
// Each line below is one polaroid frame, from top to bottom.
//   t   = the title written under the photo
//   s   = YOUR STORY TEXT for that photo (shown on the opposite side of the frame)
//   img = PUT YOUR PHOTO HERE: between the two quote marks, paste the photo's file name
//         (for example img:'photo1.jpg') or a full image link (https://...).
//         Leave it empty ('') to keep the pink heart placeholder.
// To add or remove a frame, add or delete one line (keep the comma at the end).
var STORY=[
  {t:'How we met', img:'https://github.com/maxiimaxin-art/happy-birthday-/blob/main/WhatsApp%20Image%202026-11-07%20at%2010.07.56%20PM.jpeg?raw=true',   // <-- photo 1 goes inside the quotes
   s:'We met when we were in KG. That’s when I saw her for the first time. She was the only friend I had. At that time I didn’t realize that I was going to fall in love with her.'},
  {t:'Our first meet', img:'https://github.com/maxiimaxin-art/happy-birthday-/blob/main/WhatsApp%20Image%202026-11-07%20at%208.15.37%20PM%20(1).jpeg?raw=true',   // <-- photo 2
   s:'After that, I met her again after fourteen years. At that time, she didn’t recognize me, but I remembered her. She didn’t know that she was going to fall in love with me. But that moment was really nice.'},
  {t:'Our first bike ride', img:'https://github.com/maxiimaxin-art/happy-birthday-/blob/main/WhatsApp%20Image%202026-11-07%20at%208.15.37%20PM%20(2).jpeg?raw=true',   // <-- photo 3
   s:'I don’t even have words for it. For her… when we went for a ride together for the first time, the smile on her face is still in my mind. She was so happy.'},
  {t:'Our favourite place', img:'https://github.com/maxiimaxin-art/happy-birthday-/blob/main/WhatsApp%20Image%202026-11-07%20at%208.15.37%20PM%20(4).jpeg?raw=true',   // <-- photo 4
   s:'We don’t have a favorite place. Wherever we’re together, wherever we’re sitting together, that’s our favorite place. For me, she is my favorite place. Being with her.'},
  {t:'Laughing together', img:'https://github.com/maxiimaxin-art/happy-birthday-/blob/main/WhatsApp%20Image%202026-11-07%20at%208.15.37%20PM%20(3).jpeg?raw=true',   // <-- photo 5
   s:'Maybe we’re far apart from each other. But whenever we do come together, what I always remember from those times is us smiling.'},
  {t:'Forever to go', img:'https://github.com/maxiimaxin-art/happy-birthday-/blob/main/WhatsApp%20Image%202026-11-07%20at%208.15.37%20PM.jpeg?raw=true',   // <-- photo 6
   s:'I just want one thing in life. I want you to be with me. Just like this, with our hands holding each other’s, I want us to stay together till the very end, and keep living life together.'}
];
var chain=$('chain'),IH=300;
(function(){
  var n=STORY.length,H=n*IH,h='',j,y,d='M40 0 Q68 75 40 150';
  for(j=2;j<=H/150;j++)d+=' T40 '+(150*j);
  chain.style.height=H+'px';
  h+='<svg class="br" width="80" height="'+H+'" viewBox="0 0 80 '+H+'"><path d="'+d+'" fill="none" stroke="#6b4129" stroke-width="9" stroke-linecap="round"/><path d="'+d+'" fill="none" stroke="#a9744c" stroke-width="3" stroke-linecap="round" transform="translate(-1.5 0)"/></svg>';
  var cols=['#ff8fb0','#ffffff','#ffb3c9','#ff5d8a'];
  function flower(c,s){var p='';[0,72,144,216,288].forEach(function(a){p+='<ellipse cx="12" cy="6" rx="3.6" ry="5.2" transform="rotate('+a+' 12 12)"/>'});return '<svg viewBox="0 0 24 24" width="'+s+'" height="'+s+'"><g fill="'+c+'" stroke="#e0a0b5" stroke-width=".4">'+p+'</g><circle cx="12" cy="12" r="3" fill="#ffd45e"/></svg>'}
  for(y=36,j=0;y<H-20;y+=62,j++){
    var side=j%2?1:-1,dx=side*(12+Math.random()*12),s=16+Math.random()*9;
    h+='<div class="fl" style="top:'+(y-s/2)+'px;left:calc(50% + '+(dx-s/2)+'px);transition-delay:'+(Math.random()*.4)+'s">'+flower(cols[j%cols.length],s)+'</div>';
    h+='<div class="lf" style="top:'+(y+24)+'px;left:calc(50% + '+(-side*14-8)+'px);--lr:'+(-side*35)+'deg"></div>';
  }
  STORY.forEach(function(it,i){
    var L=i%2===0,r=(L?-1:1)*(2+(i%3)*1.5);
    h+='<div class="item '+(L?'L':'R')+'" style="top:'+(i*IH)+'px"><div class="twig"><svg viewBox="0 0 100 20" preserveAspectRatio="none"><path d="M100 3Q55 -3 0 14" fill="none" stroke="#6b4129" stroke-width="5" stroke-linecap="round" vector-effect="non-scaling-stroke"/></svg></div><div class="pol" style="--r:'+r+'deg"><div class="ph">'+(it.img?'<img src="'+it.img+'" alt="'+it.t+'" onerror="this.parentNode.textContent=String.fromCharCode(9829)">':'&#9829;')+'</div><div class="cap">'+it.t+'</div></div><div class="story">'+it.s+'</div></div>';
  });
  chain.innerHTML=h;
})();
function watch(){
  var io=new IntersectionObserver(function(es){var k=0;es.forEach(function(e){
    if(!e.isIntersecting)return;
    e.target.classList.add('in');
    if(e.target.classList.contains('pol'))e.target.style.animationDelay=(k++*0.4)+'s';
    io.unobserve(e.target);
  })},{root:p2,threshold:.3});
  chain.querySelectorAll('.pol,.story,.fl,.lf').forEach(function(x){io.observe(x)});
}
document.addEventListener('pointerup',function(){
  if(!ready||going)return;going=true;
  document.body.classList.add('go');
  var W=innerWidth,H=innerHeight,cols=['#ff7fa3','#ff5d8a','#e63e78','#ffb3c9','#d6336c'];
  for(var i=0;i<70;i++){(function(i){
    var left=i%2===0,s=18+Math.random()*44,el=document.createElement('div');
    el.className='fh';el.textContent='\u2665';el.style.fontSize=s+'px';el.style.color=cols[i%cols.length];
    var y=Math.random()*H,x0=left?-s*2:W+s*2,x1=(left?.15+Math.random()*.4:.45+Math.random()*.4)*W,y1=y+(Math.random()*160-80);
    document.body.appendChild(el);
    var an=el.animate([
      {transform:'translate('+x0+'px,'+y+'px) rotate('+(left?-30:30)+'deg)',opacity:1},
      {transform:'translate('+x1+'px,'+y1+'px) rotate(0deg)',opacity:1,offset:.7},
      {transform:'translate('+(x1+(left?60:-60))+'px,'+(y1-40)+'px) rotate(0deg) scale(1.4)',opacity:0}
    ],{duration:1800+Math.random()*1200,delay:Math.random()*900,easing:'ease-out',fill:'both'});
    an.onfinish=function(){el.remove()};
  })(i)}
  setTimeout(function(){p2.classList.add('show');watch()},1500);
});
// ---- Bouncing heart at the end of page 2: it hops, balloons up in front of the screen, bursts, then page 3 appears
var hb=$('hb'),p3=$('p3');
hb.addEventListener('click',function(){
  if(hb.dataset.d)return;hb.dataset.d=1;
  var r=hb.getBoundingClientRect(),sx=r.left+r.width/2,sy=r.top+r.height/2,W=innerWidth,H=innerHeight,cx=W/2,cy=H/2;
  hb.style.visibility='hidden';
  var el=document.createElement('div');el.className='bh';
  el.innerHTML='<svg viewBox="0 0 100 90"><defs><radialGradient id="g2" cx="35%" cy="30%" r="80%"><stop offset="0" stop-color="#ffb3c9"/><stop offset=".5" stop-color="#ff5d8a"/><stop offset="1" stop-color="#b3123f"/></radialGradient></defs><path d="M50 86C8 56-2 30 14 14C29 0 46 8 50 22C54 8 71 0 86 14C102 30 92 56 50 86Z" fill="url(#g2)" stroke="rgba(255,255,255,.6)" stroke-width="1.2"/><ellipse cx="30" cy="24" rx="10" ry="6" transform="rotate(-35 30 24)" fill="#fff" opacity=".55"/></svg>';
  document.body.appendChild(el);
  function T(x,y,a,b){return 'translate('+x+'px,'+y+'px) translate(-50%,-50%) scale('+a+','+(b||a)+')'}
  var an=el.animate([
    {transform:T(sx,sy,.45),offset:0,easing:'ease-out'},
    {transform:T(cx,cy-80,1),offset:.22,easing:'ease-in'},
    {transform:T(cx,cy+20,1.2,.85),offset:.34,easing:'ease-out'},
    {transform:T(cx,cy-120,1.5),offset:.48,easing:'ease-in'},
    {transform:T(cx,cy+30,1.8,1.45),offset:.6,easing:'ease-out'},
    {transform:T(cx,cy-90,2.2),offset:.74,easing:'ease-in'},
    {transform:T(cx,cy+20,2.7,2.2),offset:.85,easing:'ease-out'},
    {transform:T(cx,cy,3.1),offset:1}
  ],{duration:2400,fill:'forwards'});
  an.onfinish=function(){
    el.remove();
    var f=document.createElement('div');f.className='flash';document.body.appendChild(f);setTimeout(function(){f.remove()},900);
    var cols=['#ff7fa3','#ff5d8a','#e63e78','#ffb3c9','#d6336c','#e8a33d','#a67cff'],reach=Math.hypot(W,H)/2;
    for(var i=0;i<120;i++){(function(i){
      var q=document.createElement('div'),heartP=i%3!==0,c=cols[i%cols.length];
      q.className='fh';q.style.zIndex=10;
      if(heartP){q.textContent='\u2665';q.style.fontSize=(14+Math.random()*38)+'px';q.style.color=c}
      else{q.style.width=(8+Math.random()*8)+'px';q.style.height=(5+Math.random()*4)+'px';q.style.background=c;q.style.borderRadius='2px'}
      document.body.appendChild(q);
      var ang=Math.random()*Math.PI*2,dist=(.5+Math.random()*.9)*reach*1.1,dx=Math.cos(ang)*dist,dy=Math.sin(ang)*dist,rot=Math.random()*540-270;
      var P=function(x,y,s,rt){return 'translate('+cx+'px,'+cy+'px) translate(-50%,-50%) translate('+x+'px,'+y+'px) scale('+s+') rotate('+rt+'deg)'};
      var a2=q.animate([
        {transform:P(0,0,.3,0),opacity:1},
        {transform:P(dx,dy,1,rot),opacity:1,offset:.7},
        {transform:P(dx*1.1,dy*1.1+90,.8,rot*1.2),opacity:0}
      ],{duration:1300+Math.random()*900,easing:'cubic-bezier(.1,.8,.3,1)',fill:'forwards'});
      a2.onfinish=function(){q.remove()};
    })(i)}
    setTimeout(function(){
      p2.classList.remove('show');p3.classList.add('show');
      setTimeout(function(){p2.style.display='none'},1500);
    },600);
  };
});
// ---- Page 3: the bear asks "Do you love me?" ----
var sp=$('sp'),row=$('row'),yes=$('yes'),no=$('no'),bear=$('bear'),saidYes=false;
function dodge(e){
  if(saidYes)return;e.preventDefault();
  var w=innerWidth,h=innerHeight,r=no.getBoundingClientRect();
  no.style.position='fixed';no.style.animation='none';no.style.opacity=1;
  no.style.left=Math.max(10,Math.random()*(w-r.width-20))+'px';
  no.style.top=Math.max(10,Math.random()*(h-r.height-20))+'px';
  sp.textContent='Are you sure? Try again \u2665';
}
no.addEventListener('pointerdown',dodge);no.addEventListener('mouseenter',dodge);no.addEventListener('click',dodge);
yes.addEventListener('click',function(){
  if(saidYes)return;saidYes=true;
  sp.textContent='I love you too, my queen \u2665';
  row.style.opacity=0;row.style.pointerEvents='none';no.style.display='none';
  bear.classList.add('happy');
  var r=bear.getBoundingClientRect(),cx=r.left+r.width/2,cy=r.top+r.height/2,cols=['#ff5d8a','#ff8fb0','#e63e78','#ffb3c9','#d6336c'];
  var ring=document.createElement('div');ring.className='ring';ring.style.left=cx+'px';ring.style.top=cy+'px';ring.style.zIndex=9;document.body.appendChild(ring);setTimeout(function(){ring.remove()},1000);
  for(var i=0;i<60;i++){(function(i){
    var h=document.createElement('div');h.className='fh';h.textContent='\u2665';h.style.zIndex=10;
    h.style.fontSize=(14+Math.random()*30)+'px';h.style.color=cols[i%cols.length];document.body.appendChild(h);
    var ang=Math.random()*Math.PI*2,dist=90+Math.random()*190,dx=Math.cos(ang)*dist,dy=Math.sin(ang)*dist;
    var a=h.animate([
      {transform:'translate('+cx+'px,'+cy+'px) scale(.3)',opacity:1},
      {transform:'translate('+(cx+dx)+'px,'+(cy+dy)+'px) scale(1)',opacity:1,offset:.7},
      {transform:'translate('+(cx+dx*1.1)+'px,'+(cy+dy*1.1+60)+'px) scale(.8)',opacity:0}
    ],{duration:1200+Math.random()*800,easing:'cubic-bezier(.1,.8,.3,1)',fill:'forwards'});
    a.onfinish=function(){h.remove()};
  })(i)}
  for(var k=0;k<45;k++){(function(k){
    var h=document.createElement('div');h.className='fh';h.textContent='\u2665';h.style.zIndex=10;
    h.style.fontSize=(14+Math.random()*24)+'px';h.style.color=cols[k%cols.length];document.body.appendChild(h);
    var x=Math.random()*innerWidth,a=h.animate([
      {transform:'translate('+x+'px,-40px) rotate(0deg)',opacity:1},
      {transform:'translate('+(x+Math.random()*80-40)+'px,'+(innerHeight+40)+'px) rotate('+(Math.random()*360-180)+'deg)',opacity:1}
    ],{duration:3000+Math.random()*2500,delay:600+Math.random()*3500,easing:'ease-in',fill:'both'});
    a.onfinish=function(){h.remove()};
  })(k)}
});
// ---- Make the bear tappable after she says yes -> page 4 (golden envelope)
yes.addEventListener('click',function(){setTimeout(function(){row.style.display='none';$('bhint').style.opacity=1},3000)});
var go4=false,p4=$('p4');
bear.addEventListener('click',function(){
  if(!saidYes||go4)return;go4=true;
  p3.classList.remove('show');p4.classList.add('show');
  setTimeout(function(){p3.style.display='none'},1500);
});
// ---- Page 4: golden envelope. Edit the words she will read here (one line = one paragraph):
var LETTER=[
'Libia Chellame wish you’re many more happy returns of the day my dear..👸🏻🫂💕',
'inthe year onaku periya periya happiness kondu tharum Chllo… ♾️💕ne nenaikure ellame inthe year nadakum Chllo…..🫶🏻',
'ne epovume Siruchute irrukanum Chllo… onaku life le inime Oru kastamum varathu Chllo apdi vanthalum enna thandanum Chllo oh kuda na epovume irrupe Chllo…. 🫂',
'Enkau ne en life le kanavule mattuthe ne varuve nu nenachu nenachu Oru 13 years ona mattu nenachutu irrunthe Chllo….but anthe kadavuluku na ona mattu nenechutu irrunthathu purinju irruku…. en manasule oh mela irruntha love god ku therinju irruku chllo….🫀 enaku kadavul kuduthe varam chllo…. Oh kudave epovum irrukanum ona bathrema happy ah vachu pathukanum nu tha enaku aase chllo 💞',
'inthe life full ah oh kuda mattu spend pannanu Chllo 💓 en thangathoda ella highs and lows le na kuda irrupe Chllo',
'Ipo ne sirikure marii epovum sirikanun Chllo 🤍 sikroo ona official ah enkau sonthamakure Chllo athu vare kojoo wait pannu pothum 💖 and chlloo i love you more and more every second of my life time Pattuma ❤️🩷❤️🧡 once more happy birthday day Chellakutty 💝',
'Innu mudiyala Chllo Innu irruku paaru onaku gifts irruku enjoy with your gifts my dear 🩷🩷🩷🎁🎁🎁🎁'
];
$('lt').innerHTML=LETTER.map(function(t){return '<p>'+t+'</p>'}).join('');
var env2=$('env2'),seal=$('seal');
function heartShower(){
  var W=innerWidth,H=innerHeight,cols=['#ff7fa3','#ff5d8a','#e63e78','#ffb3c9','#d6336c','#ff8fb0'];
  for(var i=0;i<110;i++){(function(i){
    var left=i%2===0,sz=16+Math.random()*34,el=document.createElement('div');
    el.className='fh';el.textContent='\u2665';el.style.fontSize=sz+'px';el.style.color=cols[i%cols.length];el.style.zIndex=9;
    document.body.appendChild(el);
    var x0=left?-sz*2:W+sz*2,y0=H*(Math.random()*1.05),
        x1=(left?.12+Math.random()*.4:.48+Math.random()*.4)*W,y1=y0+Math.random()*H*.15,
        x2=x1+(Math.random()*120-60),y2=H+60;
    var an=el.animate([
      {transform:'translate('+x0+'px,'+y0+'px) rotate('+(left?-30:30)+'deg)',opacity:1,easing:'ease-out'},
      {transform:'translate('+x1+'px,'+y1+'px) rotate(0deg)',opacity:1,offset:.35,easing:'ease-in'},
      {transform:'translate('+x2+'px,'+y2+'px) rotate('+(Math.random()*120-60)+'deg)',opacity:.9}
    ],{duration:2800+Math.random()*1800,delay:Math.random()*1600,fill:'both'});
    an.onfinish=function(){el.remove()};
  })(i)}
}
for(var g=0;g<20;g++){var gl=document.createElement('span');gl.className='gl';gl.textContent='\u2726';gl.style.left=(6+Math.random()*88)+'%';gl.style.top=(5+Math.random()*90)+'%';gl.style.fontSize=(10+Math.random()*14)+'px';gl.style.animationDelay=(Math.random()*2.4)+'s';env2.appendChild(gl)}
// ====== SONG SETTINGS ======
// The song plays from the very beginning at the moment the arrow bursts the heart on page 1.
// SONG_SRC = the path of the mp3 inside your GitHub repository, written relative to this file.
//   Same folder as index.html:      'kannukulla.mp3'
//   Inside a folder called music:   'music/kannukulla.mp3'
//   Use lowercase letters and no spaces (GitHub file names are case-sensitive).
var SONG_SRC='kannukulla.mp3',song=null,songStarted=false;
// On her first touch we quietly prepare the audio, because phones only allow sound after a touch.
function unlockSong(){
  if(song)return;
  try{
    song=new Audio(SONG_SRC);song.preload='ID3';song.muted=true;
    var pr=song.play();
    if(pr&&pr.then)pr.then(function(){if(!songStarted){song.pause();song.currentTime=0}song.muted=false}).catch(function(){song.muted=false});
  }catch(e){}
}
function playSong(){
  if(songStarted)return;songStarted=true;
  try{
    if(!song)song=new Audio(SONG_SRC);
    song.muted=false;song.currentTime=0;
    var pr=song.play();if(pr&&pr.catch)pr.catch(function(){});
  }catch(e){}
}
document.addEventListener('pointerdown',unlockSong,{once:true});
seal.addEventListener('click',function(){
  if(env2.classList.contains('open'))return;
  env2.classList.add('open');
  heartShower();
  setTimeout(function(){env2.classList.add('gone')},1500);
  setTimeout(function(){env2.style.display='none';p4.classList.add('opened')},2400);
  setTimeout(function(){$('toGifts').classList.add('on')},6500);
});
// ================= PAGE 5: THREE GIFT BOXES =================
// The videos for the gifts. Upload them to your GitHub repository and write their paths here (same folder: 'gift1.mp4', in a folder: 'videos/gift1.mp4').
var VIDEOS=['https://raw.githubusercontent.com/maxiimaxin-art/happy-birthday-/0009c9345fdc669a09737203669f915654c2dda1/surprice.mp4'];
var p5=$('p5'),g5s=$('g5s'),giftsEl=$('gifts'),vidov=$('vidov'),gv=$('gv'),vplay=$('vplay'),vend=$('vend'),vnext=$('vnext');
var cur=0,busy=false,wasSong=false,vStarted=false,vErr=false;
var GC=[['#e63e78','#ff7fa3']];
function giftSVG(c){return '<svg viewBox="0 0 120 130"><ellipse cx="60" cy="124" rx="44" ry="5" fill="rgba(90,40,60,.18)"/><g><rect x="20" y="64" width="80" height="58" rx="4" fill="'+c[0]+'"/><rect x="54" y="64" width="12" height="58" fill="#ffe08a"/><ellipse class="glow" cx="60" cy="66" rx="34" ry="7" fill="#fff6c8"/></g><g class="lid"><rect x="14" y="46" width="92" height="22" rx="4" fill="'+c[1]+'"/><rect x="54" y="46" width="12" height="22" fill="#ffe08a"/><path d="M60 46Q36 16 27 32Q25 46 60 46Z" fill="#ffd45e" stroke="#e0a82e" stroke-width="1.5"/><path d="M60 46Q84 16 93 32Q95 46 60 46Z" fill="#ffd45e" stroke="#e0a82e" stroke-width="1.5"/><circle cx="60" cy="44" r="6" fill="#ffc43a"/></g></svg>'}
GC.forEach(function(c,i){var b=document.createElement('button');b.className='gift';b.setAttribute('aria-label','Gift '+(i+1));b.innerHTML=giftSVG(c)+'<span class="gn">'+(i+1)+'</span>';giftsEl.appendChild(b)});
var giftBtns=giftsEl.querySelectorAll('.gift');
function setStates(){giftBtns.forEach(function(g,i){g.classList.toggle('open',i<cur);g.classList.toggle('ready',i===cur);g.classList.toggle('locked',i>cur)})}
setStates();
$('toGifts').addEventListener('click',function(){
  p4.classList.remove('show');p5.classList.add('show');
  setTimeout(function(){p4.style.display='none'},1500);
});
function heartsAround(el){
  var r=el.getBoundingClientRect(),x0=r.left+r.width/2,y0=r.top+r.height*.4;
  for(var i=0;i<18;i++){(function(i){
    var h=document.createElement('div');h.className='fh';h.textContent='\u2665';h.style.zIndex=10;
    h.style.fontSize=(14+Math.random()*20)+'px';h.style.color=['#ff5d8a','#ff8fb0','#e63e78'][i%3];document.body.appendChild(h);
    var ang=Math.random()*Math.PI*2,d=50+Math.random()*90;
    var a=h.animate([{transform:'translate('+x0+'px,'+y0+'px) scale(.3)',opacity:1},{transform:'translate('+(x0+Math.cos(ang)*d)+'px,'+(y0+Math.sin(ang)*d-40)+'px) scale(1)',opacity:0}],{duration:900+Math.random()*500,easing:'ease-out',fill:'forwards'});
    a.onfinish=function(){h.remove()};
  })(i)}
}
giftBtns.forEach(function(g,i){g.addEventListener('click',function(){
  if(busy||i<cur)return;
  if(i>cur){g5s.textContent='Open them one by one \u2665';return}
  openGift(i,g);
})});
function openGift(i,g){
  busy=true;vStarted=false;vErr=false;g.classList.add('opening');heartsAround(g);
  gv.src=VIDEOS[i];gv.muted=true;
  var pr=gv.play();
  if(pr&&pr.then)pr.then(function(){if(!vStarted){gv.pause();gv.currentTime=0}}).catch(function(){});
  setTimeout(function(){
    vend.classList.remove('on');vplay.classList.remove('on');vidov.classList.add('on');
    if(typeof song!=='undefined'&&song&&!song.paused){song.pause();wasSong=true}
    vStarted=true;gv.muted=false;gv.currentTime=0;
    var p2=gv.play();if(p2&&p2.catch)p2.catch(function(){if(gv.error||vErr)vend.classList.add('on');else vplay.classList.add('on')});
    if(vErr||gv.error)vend.classList.add('on');
    setTimeout(function(){vend.classList.add('on')},40000);
  },1100);
}
vplay.addEventListener('click',function(){vplay.classList.remove('on');gv.muted=false;var p=gv.play();if(p&&p.catch)p.catch(function(){})});
gv.addEventListener('ended',function(){vend.classList.add('on')});
gv.addEventListener('error',function(){vErr=true;if(vidov.classList.contains('on'))vend.classList.add('on')});
vnext.addEventListener('click',function(){
  vidov.classList.remove('on');vend.classList.remove('on');gv.pause();
  if(wasSong&&song){var pp=song.play();if(pp&&pp.catch)pp.catch(function(){});wasSong=false}
  cur++;setStates();busy=false;
  goBalloon();
});
// ================= PAGE 6: balloon proposal =================
var p6=$('p6'),bal6=$('bal6'),gun6=$('gun6'),b6t=$('b6t'),g6h=$('g6h'),stage6=$('stage6'),sm=$('sm'),q6=$('q6'),fin6=$('fin6'),y6=$('y6'),n6=$('n6'),q6s=$('q6s');
var shot6=false,on6=false,saidYes6=false;
bal6.innerHTML='<svg viewBox="0 0 120 190"><defs><radialGradient id="bgr" cx="35%" cy="30%" r="80%"><stop offset="0" stop-color="#ffb3c9"/><stop offset=".5" stop-color="#ff5d8a"/><stop offset="1" stop-color="#b3123f"/></radialGradient></defs><path d="M60 120C14 86 6 50 24 30C40 12 58 22 60 38C62 22 80 12 96 30C114 50 106 86 60 120Z" fill="url(#bgr)" stroke="rgba(255,255,255,.5)" stroke-width="1.2"/><ellipse cx="38" cy="42" rx="11" ry="6" transform="rotate(-35 38 42)" fill="#fff" opacity=".55"/><polygon points="53,126 67,126 60,114" fill="#c2183f"/><path d="M60 126Q50 144 62 160T58 188" fill="none" stroke="#9a8f95" stroke-width="1.6"/></svg>';
gun6.innerHTML='<svg viewBox="0 0 140 90"><path d="M64 40H94L88 84H62Z" fill="#ffb3c9" stroke="#b03a63" stroke-width="2.5" stroke-linejoin="round"/><path d="M78 58q4-5 8 0q-2 5-4 7q-2-2-4-7z" fill="#e63e78"/><rect x="40" y="14" width="92" height="28" rx="9" fill="#ff8fb0" stroke="#b03a63" stroke-width="2.5"/><rect x="108" y="22" width="24" height="12" rx="4" fill="#ffd45e" stroke="#b07a10" stroke-width="2"/><rect x="50" y="20" width="44" height="6" rx="3" fill="#fff" opacity=".6"/><path d="M70 42Q66 62 82 58" fill="none" stroke="#b03a63" stroke-width="3" stroke-linecap="round"/><rect x="76" y="42" width="4" height="10" rx="2" fill="#b03a63"/></svg>';
function goBalloon(){
  p5.classList.remove('show');p6.classList.add('show');
  setTimeout(function(){p5.style.display='none'},1500);
  var W=innerWidth;
  bal6.style.display='block';bal6.style.left=(W/2-bal6.offsetWidth/2)+'px';
  gun6.style.display='block';var sc=gun6.offsetWidth/140;gun6.style.left=(W/2+17*sc-gun6.offsetWidth/2)+'px';
  gun6.animate([{transform:'translateY(220px) rotate(-90deg)'},{transform:'translateY(0) rotate(-90deg)'}],{duration:900,delay:600,easing:'cubic-bezier(.2,.8,.2,1)',fill:'backwards'});
  var ba=bal6.animate([{transform:'translateY(100vh)'},{transform:'translateY(0)'}],{duration:2200,delay:600,easing:'cubic-bezier(.2,.8,.2,1)',fill:'backwards'});
  ba.onfinish=function(){bal6.classList.add('float');on6=true;g6h.style.opacity=1};
}
function shoot6(){
  if(shot6||!on6)return;shot6=true;g6h.style.opacity=0;
  var br=bal6.getBoundingClientRect(),by=br.top+br.height*.38;
  var gr=gun6.getBoundingClientRect(),sc=gun6.offsetWidth/140,mx=gr.left+gr.width/2-17*sc,my=gr.top+gr.height/2-62*sc;
  var bx=br.left+br.width/2;
  gun6.animate([{transform:'rotate(-90deg) translateX(0)'},{transform:'rotate(-90deg) translateX(-16px)'},{transform:'rotate(-90deg) translateX(0)'}],{duration:260});
  var fl=document.createElement('div');fl.className='fh';fl.textContent='\u2736';fl.style.cssText+=';font-size:46px;color:#ffd45e;z-index:11;text-shadow:0 0 14px #fff';document.body.appendChild(fl);
  fl.animate([{transform:'translate('+mx+'px,'+my+'px) translate(-50%,-50%) scale(.4)',opacity:1},{transform:'translate('+mx+'px,'+my+'px) translate(-50%,-50%) scale(1.5)',opacity:0}],{duration:260,fill:'forwards'}).onfinish=function(){fl.remove()};
  var bu=document.createElement('div');bu.className='fh';bu.style.cssText+=';width:14px;height:14px;border-radius:50%;background:#ffd45e;box-shadow:0 0 10px #ff8fb0;z-index:11';document.body.appendChild(bu);
  var total=my+40,dur=Math.max(380,total/2);
  bu.animate([{transform:'translate('+mx+'px,'+my+'px) translate(-50%,-50%)'},{transform:'translate('+mx+'px,-40px) translate(-50%,-50%)'}],{duration:dur,easing:'linear',fill:'forwards'}).onfinish=function(){bu.remove()};
  setTimeout(function(){pop6(bx,by)},dur*(my-by)/total);
}
gun6.addEventListener('click',shoot6);
gun6.addEventListener('keydown',function(e){if(e.key==='Enter'||e.key===' '){e.preventDefault();shoot6()}});
function pop6(bx,by){
  bal6.style.display='none';b6t.style.opacity=0;
  if(navigator.vibrate)navigator.vibrate(60);
  var f=document.createElement('div');f.className='flash';document.body.appendChild(f);setTimeout(function(){f.remove()},900);
  var rg=document.createElement('div');rg.className='ring';rg.style.left=bx+'px';rg.style.top=by+'px';rg.style.zIndex=9;document.body.appendChild(rg);setTimeout(function(){rg.remove()},1000);
  var W=innerWidth,H=innerHeight,reach=Math.hypot(W,H)/2,cols=['#ff5d8a','#ff8fb0','#e63e78','#ffb3c9','#ffd45e','#a67cff','#4fb3e8'];
  for(var i=0;i<110;i++){(function(i){
    var q=document.createElement('div'),t=i%3,c=cols[i%cols.length];q.className='fh';q.style.zIndex=10;
    if(t===0){q.textContent='\u2665';q.style.fontSize=(14+Math.random()*34)+'px';q.style.color=c}
    else if(t===1){q.style.width=(8+Math.random()*8)+'px';q.style.height=(5+Math.random()*5)+'px';q.style.background=c;q.style.borderRadius='2px'}
    else{q.style.width=q.style.height=(14+Math.random()*10)+'px';q.style.background='#ff5d8a';q.style.clipPath='polygon(0 0,100% 40%,30% 100%)'}
    document.body.appendChild(q);
    var ang=Math.random()*Math.PI*2,dist=(.35+Math.random()*.8)*reach,dx=Math.cos(ang)*dist,dy=Math.sin(ang)*dist,rot=Math.random()*540-270;
    var P=function(x,y,s,r){return 'translate('+bx+'px,'+by+'px) translate(-50%,-50%) translate('+x+'px,'+y+'px) scale('+s+') rotate('+r+'deg)'};
    q.animate([{transform:P(0,0,.3,0),opacity:1},{transform:P(dx,dy,1,rot),opacity:1,offset:.65},{transform:P(dx*1.1,dy*1.1+120,.8,rot*1.2),opacity:0}],{duration:1400+Math.random()*1100,easing:'cubic-bezier(.1,.8,.3,1)',fill:'forwards'}).onfinish=function(){q.remove()};
  })(i)}
  var pt=document.createElement('div');pt.className='popt';pt.textContent='POP!';document.body.appendChild(pt);
  pt.animate([{transform:'translate('+bx+'px,'+by+'px) translate(-50%,-50%) scale(.3)',opacity:1},{transform:'translate('+bx+'px,'+by+'px) translate(-50%,-50%) scale(1.4)',opacity:1,offset:.35},{transform:'translate('+bx+'px,'+(by-60)+'px) translate(-50%,-50%) scale(1.1)',opacity:0}],{duration:1100,fill:'forwards'}).onfinish=function(){pt.remove()};
  gun6.animate([{opacity:1},{opacity:0}],{duration:600,delay:700,fill:'forwards'});
  setTimeout(function(){stage6.classList.add('on')},1700);
}
sm.addEventListener('click',function(){
  sm.style.display='none';q6.style.display='flex';
});
function dodge6(e){
  if(saidYes6)return;e.preventDefault();e.stopPropagation();
  var w=innerWidth,h=innerHeight,r=n6.getBoundingClientRect();
  n6.style.position='fixed';n6.style.animation='none';n6.style.opacity=1;n6.style.zIndex=9;
  n6.style.left=Math.max(10,Math.random()*(w-r.width-20))+'px';
  n6.style.top=Math.max(10,Math.random()*(h-r.height-20))+'px';
  q6s.textContent='Nice try \u2665';
}
n6.addEventListener('pointerdown',dodge6);n6.addEventListener('mouseenter',dodge6);n6.addEventListener('click',dodge6);
function shower4(){
  var W=innerWidth,H=innerHeight,cols=['#ff5d8a','#ff8fb0','#e63e78','#ffb3c9','#d6336c','#ff7fa3'];
  for(var side=0;side<4;side++){for(var i=0;i<32;i++){(function(side,i){
    var sz=16+Math.random()*30,h=document.createElement('div');h.className='fh';h.textContent='\u2665';h.style.fontSize=sz+'px';h.style.color=cols[i%cols.length];h.style.zIndex=10;document.body.appendChild(h);
    var x0,y0,x1,y1,jit=Math.random()*H,jx=Math.random()*W;
    if(side===0){x0=jx;y0=-sz*2;x1=W-jx+(Math.random()*160-80);y1=H*(.4+Math.random()*.6)}
    else if(side===1){x0=jx;y0=H+sz*2;x1=W-jx+(Math.random()*160-80);y1=H*(Math.random()*.6)}
    else if(side===2){x0=-sz*2;y0=jit;x1=W*(.4+Math.random()*.6);y1=H-jit+(Math.random()*160-80)}
    else{x0=W+sz*2;y0=jit;x1=W*(Math.random()*.6);y1=H-jit+(Math.random()*160-80)}
    h.animate([{transform:'translate('+x0+'px,'+y0+'px) rotate(0deg)',opacity:1},{transform:'translate('+x1+'px,'+y1+'px) rotate('+(Math.random()*120-60)+'deg)',opacity:.9}],{duration:2800+Math.random()*2200,delay:Math.random()*2400,easing:'ease-out',fill:'both'}).onfinish=function(){h.remove()};
  })(side,i)}}
}
y6.addEventListener('click',function(){
  if(saidYes6)return;saidYes6=true;
  n6.style.display='none';q6.style.display='none';fin6.style.display='block';
  shower4();var n=0,iv=setInterval(function(){shower4();if(++n>=2)clearInterval(iv)},2600);
});
</script>
</body>
</html>
