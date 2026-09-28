# gig.s
SahakarSetu MVP.html
<!DOCTYPE html>
<html lang="en"><head><meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<title>SahakarSetu</title>
<link href="https://fonts.googleapis.com/css2?family=Bricolage+Grotesque:wght@400;600;800&display=swap" rel="stylesheet">
<style>
:root{box-sizing:border-box;padding-top:env(safe-area-inset-top,0px);padding-bottom:env(safe-area-inset-bottom,0px);--bg:#eef2f0;--ink:#12233d;--mut:#5b6b7f;--card:#fff;--line:#d5dedb;--g:#1d7a5b;--gs:#d9efe6;--sf:#e9a100;--r:#c0392b}
@media(prefers-color-scheme:dark){:root:not([data-theme=light]){--bg:#0f1a1a;--ink:#e8efee;--mut:#9fb0ad;--card:#172524;--line:#2a3d3b;--g:#4fc79b;--gs:#1c3a30;--sf:#f2b53a;--r:#ff7b6b}}
:root[data-theme=dark]{--bg:#0f1a1a;--ink:#e8efee;--mut:#9fb0ad;--card:#172524;--line:#2a3d3b;--g:#4fc79b;--gs:#1c3a30;--sf:#f2b53a;--r:#ff7b6b}
html{scroll-padding-top:env(safe-area-inset-top,0px)}
*{box-sizing:border-box}
body{margin:0;background:var(--bg);color:var(--ink);font:15px/1.5 'Bricolage Grotesque',system-ui,sans-serif}
header{display:flex;flex-wrap:wrap;gap:12px;align-items:center;justify-content:space-between;padding:14px 20px;border-bottom:2px solid var(--ink)}
h1{margin:0;font-size:22px;font-weight:800;letter-spacing:-.5px}h1 span{color:var(--g)}
nav{display:flex;gap:4px}
nav button,.btn{font:inherit;border:1.5px solid var(--ink);background:transparent;color:var(--ink);padding:7px 14px;border-radius:6px;cursor:pointer;font-weight:600}
nav button.on,.btn.p{background:var(--ink);color:var(--bg)}
.btn.g{background:var(--g);border-color:var(--g);color:#fff}
.btn:disabled{opacity:.4;cursor:not-allowed}
button:focus-visible,input:focus-visible,select:focus-visible,textarea:focus-visible{outline:3px solid var(--sf);outline-offset:2px}
main{max-width:1080px;margin:0 auto;padding:20px}
.tag{color:var(--mut);margin:0 0 16px}
.grid{display:grid;gap:16px;grid-template-columns:repeat(auto-fit,minmax(300px,1fr))}
.card{background:var(--card);border:1px solid var(--line);border-radius:10px;padding:16px}
h2{margin:0 0 10px;font-size:17px}h3{margin:0 0 6px;font-size:15px}
label{display:block;font-weight:600;margin:10px 0 4px;font-size:13px}
input,select,textarea{width:100%;font:inherit;padding:8px;border:1.5px solid var(--line);border-radius:6px;background:var(--bg);color:var(--ink)}
.row{display:flex;gap:10px;align-items:center;flex-wrap:wrap}.sp{justify-content:space-between}
.w{border:1.5px solid var(--line);border-radius:8px;padding:12px;margin-top:10px}
.w.top{border-color:var(--g);background:var(--gs)}
.bar{height:8px;background:var(--line);border-radius:4px;overflow:hidden;flex:1;min-width:60px}.bar i{display:block;height:100%;background:var(--g)}.bar i.s{background:var(--sf)}
.chip{font-size:12px;padding:2px 8px;border-radius:99px;background:var(--gs);color:var(--g);font-weight:600}
.chip.a{background:#f9e6b3;color:#7a5200}
.mut{color:var(--mut);font-size:13px}
.steps{display:flex;gap:6px;margin:12px 0}.steps div{flex:1;text-align:center;font-size:12px;padding:6px 2px;border-bottom:4px solid var(--line);color:var(--mut)}.steps div.d{border-color:var(--g);color:var(--ink);font-weight:600}
.split{display:flex;height:26px;border-radius:6px;overflow:hidden;margin:10px 0;font-size:12px;font-weight:600;color:#fff}
.split div{display:flex;align-items:center;justify-content:center;transition:width .3s}
table{width:100%;border-collapse:collapse}td,th{padding:6px 4px;text-align:left;border-bottom:1px solid var(--line);font-size:14px}
.ins{border-left:5px solid var(--sf);padding:8px 12px;background:var(--card);margin-top:10px;border-radius:0 8px 8px 0}
.hide{display:none}
@media(prefers-reduced-motion:reduce){*{transition:none!important}}
</style></head><body>
<header><h1>Sahakar<span>Setu</span></h1>
<nav id="nav"><button data-t="c" class="on">Customer</button><button data-t="w">Worker</button><button data-t="a">Cooperative</button></nav></header>
<main>
<p class="tag">Digital operating layer for cooperative gig-service networks. Sample data; everything runs in your browser.</p>

<section id="c"><div class="grid">
<div class="card"><h2>Request a service</h2>
<label for="svc">Service</label><select id="svc"></select>
<label for="zone">Your area</label><select id="zone"></select>
<label for="desc">Describe the problem</label><textarea id="desc" rows="3">Kitchen pipe burst, water on the floor.</textarea>
<label class="row"><input type="checkbox" id="emg" checked style="width:auto"> Emergency (needs someone available now)</label>
<div class="row" style="margin-top:12px"><button class="btn p" id="find">Find verified workers</button><button class="btn" id="demo">Run full demo</button></div></div>
<div class="card"><h2>Fair Work Allocation</h2><p class="mut" style="margin-top:0">Adjust how the cooperative balances the factors. Workers must be verified, skilled and (for emergencies) available.</p>
<div id="wts"></div><div class="ins mut" id="alloc-note">Workload weight lifts qualified workers who have had fewer jobs this month, without dropping quality.</div></div>
</div>
<div id="res" class="card hide" style="margin-top:16px"><h2>Ranked workers</h2><div id="list"></div></div>
<div id="bk" class="card hide" style="margin-top:16px"></div></section>

<section id="w" class="hide"><div class="grid"><div class="card"><h2>Worker view</h2><label for="wsel">Signed in as</label><select id="wsel"></select><div id="wd"></div></div>
<div class="card"><h2>Incoming request</h2><div id="wreq" class="mut">No requests yet. Book a service from the Customer tab.</div></div></div></section>

<section id="a" class="hide"><div class="grid">
<div class="card"><h2>Payment split</h2><p class="mut" style="margin-top:0">Set once by the cooperative; applied to every booking.</p>
<div class="split" id="sp"></div><div id="spc"></div></div>
<div class="card"><h2>Workload this month</h2><div id="wl"></div><div class="ins mut" id="util"></div></div>
<div class="card" style="grid-column:1/-1"><h2>Demand forecast: next week</h2><div class="row"><label for="fsvc" style="margin:0">Service</label><select id="fsvc" style="width:auto"></select></div><div id="fc"></div></div>
<div class="card" style="grid-column:1/-1"><h2>Transactions</h2><div id="tx" class="mut">No transactions yet.</div></div>
</div></section>
</main>
<script>
const SV=['Plumbing','Electrical','Carpentry','Cleaning'],ZN=['Zone A','Zone B','Zone C'];
const W=[['Ravi K.','Plumbing',4.9,30,'A',1.2,1],['Sunita D.','Plumbing',4.7,10,'A',3.5,1],['Imran S.','Plumbing',4.8,22,'B',4.0,1],['Lakshmi P.','Plumbing',4.5,6,'A',2.4,0],['Manoj T.','Electrical',4.8,18,'A',2.0,1],['Farah N.','Electrical',4.6,9,'B',3.1,1],['Deepak R.','Carpentry',4.7,14,'C',2.8,1],['Geeta M.','Cleaning',4.6,12,'B',1.9,1]]
.map((a,i)=>({id:i,name:a[0],skill:a[1],rating:a[2],jobs:a[3],zone:a[4],dist:a[5],avail:!!a[6],earn:a[3]*420,certs:'Cooperative-verified'}));
const H={};SV.forEach((s,i)=>ZN.forEach((z,j)=>{const b=8+i*3+j*2,sl=(s=='Plumbing'&&j==0)?2.2:.3+((i+j)%3)*.3;H[s+z]=[0,1,2,3,4,5].map(k=>Math.round(b+sl*k+((k*7+i)%3)-1))}));
let S={split:{w:80,c:12,f:8},wt:{dist:25,load:35,rate:25,prio:15},bk:[],cur:null,sel:null,tx:[]};
const $=id=>document.getElementById(id),inr=n=>'₹'+Math.round(n).toLocaleString('en-IN');
$('svc').innerHTML=SV.map(s=>`<option>${s}</option>`).join('');$('fsvc').innerHTML=$('svc').innerHTML;
$('zone').innerHTML=ZN.map(s=>`<option>${s}</option>`).join('');
$('wsel').innerHTML=W.map(w=>`<option value="${w.id}">${w.name} (${w.skill})</option>`).join('');
document.querySelectorAll('nav button').forEach(b=>b.onclick=()=>show(b.dataset.t));
function show(t){['c','w','a'].forEach(x=>{$(x).classList.toggle('hide',x!=t)});document.querySelectorAll('nav button').forEach(b=>b.classList.toggle('on',b.dataset.t==t));if(t=='w')renderW();if(t=='a')renderA()}
function wts(){const L={dist:'Distance',load:'Fairness (lower workload)',rate:'Rating',prio:'Availability / urgency'};
$('wts').innerHTML=Object.keys(L).map(k=>`<label for="k${k}">${L[k]}: <b id="v${k}">${S.wt[k]}</b></label><input type="range" id="k${k}" min="0" max="60" value="${S.wt[k]}">`).join('');
Object.keys(L).forEach(k=>$('k'+k).oninput=e=>{S.wt[k]=+e.target.value;$('v'+k).textContent=e.target.value;if(!$('res').classList.contains('hide'))rank()})}
wts();
function rank(){const sv=$('svc').value,z=$('zone').value.slice(-1),em=$('emg').checked;const tot=Object.values(S.wt).reduce((a,b)=>a+b,0)||1;
const pool=W.filter(w=>w.skill==sv&&(!em||w.avail));const mx=Math.max(...pool.map(w=>w.jobs),1);
const r=pool.map(w=>{const f={dist:Math.max(0,1-(w.dist+(w.zone==z?0:3))/10),load:1-w.jobs/(mx*1.15),rate:(w.rating-3)/2,prio:w.avail?1:.2};
const sc=Object.keys(f).reduce((a,k)=>a+f[k]*S.wt[k],0)/tot*100;return{w,f,sc}}).sort((a,b)=>b.sc-a.sc);
S.rank=r;$('res').classList.remove('hide');
$('list').innerHTML=r.length?r.map((x,i)=>`<div class="w ${i?'':'top'}"><div class="row sp"><div><b>${x.w.name}</b> <span class="chip">Verified</span> ${x.w.avail?'<span class="chip">Available now</span>':'<span class="chip a">Busy</span>'}<div class="mut">${x.w.skill} · ★${x.w.rating} · ${x.w.dist} km · ${x.w.jobs} jobs this month · ${x.w.zone==z?'same zone':'nearby zone'}</div></div>
<div class="row"><b style="font-size:20px">${x.sc.toFixed(0)}</b><button class="btn ${i?'':'g'}" onclick="book(${x.w.id})">Book</button></div></div>
<div class="mut" style="margin-top:6px">${i==0?why(r):''}</div>
${['dist','load','rate'].map(k=>`<div class="row mut"><span style="width:92px">${{dist:'Distance',load:'Fairness',rate:'Rating'}[k]}</span><div class="bar"><i class="${k=='load'?'s':''}" style="width:${x.f[k]*100}%"></i></div></div>`).join('')}</div>`).join(''):'<p class="mut">No available verified workers for this service. Try turning off Emergency.</p>'}
function why(r){if(r.length<2)return'Only qualified worker.';const a=r[0].w,b=[...r].sort((x,y)=>y.w.jobs-x.w.jobs)[0].w;return a.id!=b.id?`Ranked first with ${a.jobs} jobs this month vs ${b.jobs} for ${b.name}, while staying strong on rating and distance.`:'Best overall fit across all factors.'}
$('find').onclick=rank;
function book(id){const w=W[id];S.cur={w,svc:$('svc').value,desc:$('desc').value,step:0,price:500,paid:false,rated:0,zone:$('zone').value};S.tx.length;renderBk();$('bk').scrollIntoView({behavior:'smooth'})}
const ST=['Requested','Accepted','On the way','Completed','Paid'];
function renderBk(){const b=S.cur;if(!b)return;$('bk').classList.remove('hide');const sp=S.split;
$('bk').innerHTML=`<h2>Booking: ${b.svc} with ${b.w.name}</h2><div class="steps">${ST.map((s,i)=>`<div class="${i<=b.step?'d':''}">${s}</div>`).join('')}</div>
<p class="mut" style="margin:0">"${b.desc}"</p>
${b.step==0?`<button class="btn p" style="margin-top:10px" onclick="adv()">Worker accepts (simulate)</button>`:''}
${b.step==1?`<button class="btn p" style="margin-top:10px" onclick="adv()">Worker on the way</button>`:''}
${b.step==2?`<button class="btn p" style="margin-top:10px" onclick="adv()">Mark service completed</button>`:''}
${b.step==3?`<h3 style="margin-top:14px">Pay ${inr(b.price)}</h3><div class="split"><div style="width:${sp.w}%;background:var(--g)">Worker ${inr(b.price*sp.w/100)}</div><div style="width:${sp.c}%;background:#3b5b8c">Co-op ${inr(b.price*sp.c/100)}</div><div style="width:${sp.f}%;background:#b07b00">Welfare ${inr(b.price*sp.f/100)}</div></div><button class="btn g" onclick="pay()">Pay digitally</button>`:''}
${b.step==4?`<div class="ins"><b>Invoice #SS-${1000+S.tx.length}</b><br>${b.svc} · ${b.w.name} · ${inr(b.price)}<br><span class="mut">Worker ${inr(b.price*sp.w/100)} · Cooperative ${inr(b.price*sp.c/100)} · Welfare fund ${inr(b.price*sp.f/100)}</span></div>
<div class="row" style="margin-top:10px">Rate:${[1,2,3,4,5].map(n=>`<button class="btn ${b.rated>=n?'p':''}" onclick="S.cur.rated=${n};renderBk()">★</button>`).join('')}</div>
<p class="mut">Worker workload and earnings updated. Check the Worker and Cooperative tabs.</p>`:''}`}
function adv(){S.cur.step++;renderBk();renderW()}
function pay(){const b=S.cur,sp=S.split;b.step=4;b.w.jobs++;b.w.earn+=b.price*sp.w/100;S.tx.push({b:{...b},w:b.w.name,svc:b.svc,amt:b.price,zone:b.zone});H[b.svc+b.zone][5]++;renderBk();renderW();renderA()}
function renderW(){const w=W[$('wsel').value];$('wd').innerHTML=`<p><b>${w.name}</b> <span class="chip">Cooperative-verified</span><br><span class="mut">${w.skill} · ${w.zone} · ★${w.rating}</span></p>
<table><tr><td>Jobs this month</td><td><b>${w.jobs}</b></td></tr><tr><td>Earnings this month</td><td><b>${inr(w.earn)}</b></td></tr><tr><td>Availability</td><td><button class="btn" onclick="W[${w.id}].avail=!W[${w.id}].avail;renderW()">${w.avail?'Available: tap to pause':'Paused: tap to go available'}</button></td></tr><tr><td>Welfare</td><td>Insurance active · fund contributions ${S.split.f}% of each job</td></tr></table>`;
const b=S.cur;$('wreq').innerHTML=b&&b.w.id==w.id&&b.step<4?`<b>${b.svc}: ${b.zone}</b><p>"${b.desc}"</p><p class="mut">Status: ${ST[b.step]} · ${inr(b.price)}</p>${b.step==0?'<button class="btn g" onclick="adv()">Accept</button> <button class="btn" onclick="S.cur=null;$(\'bk\').classList.add(\'hide\');renderW()">Reject</button>':''}`:'No requests for this worker right now.'}
$('wsel').onchange=renderW;
function renderA(){const s=S.split;$('sp').innerHTML=`<div style="width:${s.w}%;background:var(--g)">${s.w}%</div><div style="width:${s.c}%;background:#3b5b8c">${s.c}%</div><div style="width:${s.f}%;background:#b07b00">${s.f}%</div>`;
$('spc').innerHTML=`<label for="sw">Worker earnings: <b>${s.w}%</b></label><input type="range" id="sw" min="60" max="95" value="${s.w}"><label for="sf">Welfare / insurance fund: <b>${s.f}%</b></label><input type="range" id="sf" min="0" max="20" value="${s.f}"><p class="mut">Cooperative operations: ${s.c}% (remainder). On ₹500: worker ${inr(500*s.w/100)}, co-op ${inr(500*s.c/100)}, welfare ${inr(500*s.f/100)}.</p>`;
$('sw').oninput=e=>{S.split.w=+e.target.value;fix()};$('sf').oninput=e=>{S.split.f=+e.target.value;fix()};
const mx=Math.max(...W.map(w=>w.jobs));$('wl').innerHTML=W.map(w=>`<div class="row"><span style="width:90px">${w.name}</span><div class="bar"><i class="${w.jobs<12?'s':''}" style="width:${w.jobs/mx*100}%"></i></div><span class="mut" style="width:30px">${w.jobs}</span></div>`).join('');
const avg=W.reduce((a,w)=>a+w.jobs,0)/W.length,lo=W.filter(w=>w.jobs<avg*.6);$('util').textContent=lo.length?`Underutilized (below 60% of average): ${lo.map(w=>w.name).join(', ')}. The allocation engine will favor them when qualified.`:'Workload is well balanced.';
fc();$('tx').innerHTML=S.tx.length?`<table><tr><th>Service</th><th>Worker</th><th>Zone</th><th>Amount</th></tr>${S.tx.map(t=>`<tr><td>${t.svc}</td><td>${t.w}</td><td>${t.zone}</td><td>${inr(t.amt)}</td></tr>`).join('')}</table>`:'No transactions yet.'}
function fix(){const s=S.split;if(s.w+s.f>100)s.f=100-s.w;s.c=100-s.w-s.f;renderA()}
function fc(){const sv=$('fsvc').value||SV[0];let out='',best=null;
ZN.forEach(z=>{const h=H[sv+z],n=h.length,xm=(n-1)/2,ym=h.reduce((a,b)=>a+b,0)/n;let num=0,den=0;h.forEach((y,i)=>{num+=(i-xm)*(y-ym);den+=(i-xm)**2});const m=num/den,f=Math.round(ym+m*(n-xm)),last=h[n-1],ch=(f-last)/last*100,need=Math.max(0,Math.ceil(f/6)-W.filter(w=>w.skill==sv&&w.zone==z.slice(-1)).length);
if(!best||ch>best.ch)best={z,ch,need,f};
const mxv=Math.max(...h,f);out+=`<div style="flex:1;min-width:200px"><h3>${z}</h3><svg viewBox="0 0 140 60" style="width:100%;height:80px">${h.map((v,i)=>`<rect x="${i*20}" y="${58-v/mxv*54}" width="14" height="${v/mxv*54}" fill="var(--line)"/>`).join('')}<rect x="120" y="${58-f/mxv*54}" width="14" height="${f/mxv*54}" fill="var(--sf)"/></svg><div class="mut">Last 6 weeks + forecast (amber): <b>${f}</b> jobs (${ch>=0?'+':''}${ch.toFixed(0)}%)</div></div>`});
$('fc').innerHTML=`<div class="row" style="align-items:flex-start;margin-top:8px">${out}</div><div class="ins"><b>Recommendation:</b> ${sv} demand in ${best.z} is predicted to ${best.ch>=0?'increase':'fall'} by ${Math.abs(best.ch).toFixed(0)}% next week. ${best.need>0?best.need+' additional worker'+(best.need>1?'s are':' is')+' recommended there.':'Current workers can cover it.'}</div>`}
$('fsvc').onchange=fc;
$('demo').onclick=()=>{$('svc').value='Plumbing';$('zone').value='Zone A';$('emg').checked=true;$('desc').value='Emergency: kitchen pipe burst, water on the floor.';rank();book(S.rank[0].w.id);S.cur.step=0;renderBk();alert('Demo: 1) Book the top-ranked worker, 2) step through the job, 3) pay, 4) open the Cooperative tab to see workload, earnings and the demand forecast update.')}
</script></body></html>
