[index.html](https://github.com/user-attachments/files/28254763/index.html)
# Seasons<!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01//EN" "http://www.w3.org/TR/html4/strict.dtd">
<html>
<head>
  <meta http-equiv="Content-Type" content="text/html; charset=utf-8">
  <meta http-equiv="Content-Style-Type" content="text/css">
  <title></title>
  <meta name="Generator" content="Cocoa HTML Writer">
  <meta name="CocoaVersion" content="2685.4">
  <style type="text/css">
    p.p1 {margin: 0.0px 0.0px 0.0px 0.0px; font: 12.0px Helvetica}
    p.p2 {margin: 0.0px 0.0px 0.0px 0.0px; font: 12.0px Helvetica; min-height: 14.0px}
  </style>
</head>
<body>
<p class="p1">&lt;!DOCTYPE html&gt;</p>
<p class="p1">&lt;html lang="zh"&gt;</p>
<p class="p1">&lt;head&gt;</p>
<p class="p1">&lt;meta charset="UTF-8"&gt;</p>
<p class="p1">&lt;meta name="viewport" content="width=device-width, initial-scale=1.0"&gt;</p>
<p class="p1">&lt;title&gt;四季涌动&lt;/title&gt;</p>
<p class="p1">&lt;style&gt;</p>
<p class="p1"><span class="Apple-converted-space">  </span>* { margin: 0; padding: 0; box-sizing: border-box; }</p>
<p class="p1"><span class="Apple-converted-space">  </span>body { width: 100vw; height: 100vh; overflow: hidden; background: #f7cfe8; }</p>
<p class="p1"><span class="Apple-converted-space">  </span>#app { width: 100%; height: 100vh; position: relative; overflow: hidden; }</p>
<p class="p1"><span class="Apple-converted-space">  </span>canvas#bg { position: absolute; inset: 0; width: 100%; height: 100%; }</p>
<p class="p1"><span class="Apple-converted-space">  </span>#overlay {</p>
<p class="p1"><span class="Apple-converted-space">    </span>position: absolute; inset: 0; display: flex;</p>
<p class="p1"><span class="Apple-converted-space">    </span>flex-direction: column; align-items: center; justify-content: center;</p>
<p class="p1"><span class="Apple-converted-space">    </span>pointer-events: none;</p>
<p class="p1"><span class="Apple-converted-space">  </span>}</p>
<p class="p1"><span class="Apple-converted-space">  </span>#season-title {</p>
<p class="p1"><span class="Apple-converted-space">    </span>font-size: 80px; font-weight: 500; letter-spacing: -2px;</p>
<p class="p1"><span class="Apple-converted-space">    </span>transition: all 0.6s ease; text-shadow: 0 2px 24px rgba(0,0,0,0.15);</p>
<p class="p1"><span class="Apple-converted-space">    </span>font-family: sans-serif;</p>
<p class="p1"><span class="Apple-converted-space">  </span>}</p>
<p class="p1"><span class="Apple-converted-space">  </span>#season-sub {</p>
<p class="p1"><span class="Apple-converted-space">    </span>font-size: 16px; letter-spacing: 4px; text-transform: uppercase;</p>
<p class="p1"><span class="Apple-converted-space">    </span>margin-top: 10px; opacity: 0.85; transition: all 0.6s ease;</p>
<p class="p1"><span class="Apple-converted-space">    </span>font-family: sans-serif;</p>
<p class="p1"><span class="Apple-converted-space">  </span>}</p>
<p class="p1"><span class="Apple-converted-space">  </span>#nav {</p>
<p class="p1"><span class="Apple-converted-space">    </span>position: absolute; bottom: 36px; left: 50%; transform: translateX(-50%);</p>
<p class="p1"><span class="Apple-converted-space">    </span>display: flex; gap: 12px;</p>
<p class="p1"><span class="Apple-converted-space">  </span>}</p>
<p class="p1"><span class="Apple-converted-space">  </span>.s-btn {</p>
<p class="p1"><span class="Apple-converted-space">    </span>padding: 10px 24px; border-radius: 40px; border: 2px solid rgba(255,255,255,0.6);</p>
<p class="p1"><span class="Apple-converted-space">    </span>background: rgba(255,255,255,0.2); color: #fff; font-size: 16px; font-weight: 500;</p>
<p class="p1"><span class="Apple-converted-space">    </span>cursor: pointer; transition: all 0.25s; letter-spacing: 2px; font-family: sans-serif;</p>
<p class="p1"><span class="Apple-converted-space">  </span>}</p>
<p class="p1"><span class="Apple-converted-space">  </span>.s-btn:hover { background: rgba(255,255,255,0.35); transform: scale(1.07); }</p>
<p class="p1"><span class="Apple-converted-space">  </span>.s-btn.active { background: rgba(255,255,255,0.55); color: #333; border-color: #fff; }</p>
<p class="p1"><span class="Apple-converted-space">  </span>#hint {</p>
<p class="p1"><span class="Apple-converted-space">    </span>position: absolute; top: 20px; right: 20px;</p>
<p class="p1"><span class="Apple-converted-space">    </span>font-size: 13px; color: rgba(255,255,255,0.75);</p>
<p class="p1"><span class="Apple-converted-space">    </span>pointer-events: none; letter-spacing: 1px; font-family: sans-serif;</p>
<p class="p1"><span class="Apple-converted-space">  </span>}</p>
<p class="p1">&lt;/style&gt;</p>
<p class="p1">&lt;/head&gt;</p>
<p class="p1">&lt;body&gt;</p>
<p class="p1">&lt;div id="app"&gt;</p>
<p class="p1"><span class="Apple-converted-space">  </span>&lt;canvas id="bg"&gt;&lt;/canvas&gt;</p>
<p class="p1"><span class="Apple-converted-space">  </span>&lt;div id="overlay"&gt;</p>
<p class="p1"><span class="Apple-converted-space">    </span>&lt;div id="season-title"&gt;春&lt;/div&gt;</p>
<p class="p1"><span class="Apple-converted-space">    </span>&lt;div id="season-sub"&gt;Spring · 万物复苏&lt;/div&gt;</p>
<p class="p1"><span class="Apple-converted-space">  </span>&lt;/div&gt;</p>
<p class="p1"><span class="Apple-converted-space">  </span>&lt;div id="hint"&gt;移动鼠标 / 触摸屏幕&lt;/div&gt;</p>
<p class="p1"><span class="Apple-converted-space">  </span>&lt;div id="nav"&gt;</p>
<p class="p1"><span class="Apple-converted-space">    </span>&lt;button class="s-btn active" data-s="0"&gt;春&lt;/button&gt;</p>
<p class="p1"><span class="Apple-converted-space">    </span>&lt;button class="s-btn" data-s="1"&gt;夏&lt;/button&gt;</p>
<p class="p1"><span class="Apple-converted-space">    </span>&lt;button class="s-btn" data-s="2"&gt;秋&lt;/button&gt;</p>
<p class="p1"><span class="Apple-converted-space">    </span>&lt;button class="s-btn" data-s="3"&gt;冬&lt;/button&gt;</p>
<p class="p1"><span class="Apple-converted-space">  </span>&lt;/div&gt;</p>
<p class="p1">&lt;/div&gt;</p>
<p class="p2"><br></p>
<p class="p1">&lt;script&gt;</p>
<p class="p1">const SEASONS = [</p>
<p class="p1"><span class="Apple-converted-space">  </span>{</p>
<p class="p1"><span class="Apple-converted-space">    </span>name: "春", sub: "Spring · 万物复苏",</p>
<p class="p1"><span class="Apple-converted-space">    </span>bg: ["#f7cfe8","#fde4cb","#e8f5d0"],</p>
<p class="p1"><span class="Apple-converted-space">    </span>particle: { color:()=&gt;`hsl(${320+Math.random()*60},80%,70%)`, size:()=&gt;3+Math.random()*5, life:180, count:3, grav:-0.04, drag:0.99, vx:()=&gt;(Math.random()-0.5)*1.2, vy:()=&gt;-Math.random()*1.5-0.5 },</p>
<p class="p1"><span class="Apple-converted-space">    </span>titleColor: "#c2476a", subColor: "#d97a4a"</p>
<p class="p1"><span class="Apple-converted-space">  </span>},</p>
<p class="p1"><span class="Apple-converted-space">  </span>{</p>
<p class="p1"><span class="Apple-converted-space">    </span>name: "夏", sub: "Summer · 烈日炎炎",</p>
<p class="p1"><span class="Apple-converted-space">    </span>bg: ["#fff3a0","#ffe066","#a8edac"],</p>
<p class="p1"><span class="Apple-converted-space">    </span>particle: { color:()=&gt;`hsl(${40+Math.random()*30},100%,${60+Math.random()*20}%)`, size:()=&gt;2+Math.random()*4, life:80, count:5, grav:-0.08, drag:0.97, vx:()=&gt;(Math.random()-0.5)*3, vy:()=&gt;-Math.random()*3-1 },</p>
<p class="p1"><span class="Apple-converted-space">    </span>titleColor: "#b85c00", subColor: "#2d7a34"</p>
<p class="p1"><span class="Apple-converted-space">  </span>},</p>
<p class="p1"><span class="Apple-converted-space">  </span>{</p>
<p class="p1"><span class="Apple-converted-space">    </span>name: "秋", sub: "Autumn · 金风玉露",</p>
<p class="p1"><span class="Apple-converted-space">    </span>bg: ["#f5c76e","#e87a35","#c04a1a"],</p>
<p class="p1"><span class="Apple-converted-space">    </span>particle: { color:()=&gt;`hsl(${15+Math.random()*45},85%,${45+Math.random()*25}%)`, size:()=&gt;5+Math.random()*8, life:220, count:2, grav:0.06, drag:0.98, vx:()=&gt;(Math.random()-0.5)*2, vy:()=&gt;Math.random()*0.5+0.2 },</p>
<p class="p1"><span class="Apple-converted-space">    </span>titleColor: "#5a1a00", subColor: "#7a3000"</p>
<p class="p1"><span class="Apple-converted-space">  </span>},</p>
<p class="p1"><span class="Apple-converted-space">  </span>{</p>
<p class="p1"><span class="Apple-converted-space">    </span>name: "冬", sub: "Winter · 银装素裹",</p>
<p class="p1"><span class="Apple-converted-space">    </span>bg: ["#e8f0ff","#c8d8f5","#a0b8e8"],</p>
<p class="p1"><span class="Apple-converted-space">    </span>particle: { color:()=&gt;`hsl(210,${40+Math.random()*30}%,${80+Math.random()*15}%)`, size:()=&gt;2+Math.random()*5, life:300, count:4, grav:0.02, drag:0.995, vx:()=&gt;(Math.random()-0.5)*0.5, vy:()=&gt;Math.random()*0.8+0.2 },</p>
<p class="p1"><span class="Apple-converted-space">    </span>titleColor: "#1a3a7a", subColor: "#2a4a99"</p>
<p class="p1"><span class="Apple-converted-space">  </span>}</p>
<p class="p1">];</p>
<p class="p2"><br></p>
<p class="p1">let cur = 0, next = 0, t = 1, particles = [], mouse = {x:0.5, y:0.5};</p>
<p class="p1">const canvas = document.getElementById('bg');</p>
<p class="p1">const ctx = canvas.getContext('2d');</p>
<p class="p1">const app = document.getElementById('app');</p>
<p class="p2"><br></p>
<p class="p1">function resize() {</p>
<p class="p1"><span class="Apple-converted-space">  </span>canvas.width = window.innerWidth;</p>
<p class="p1"><span class="Apple-converted-space">  </span>canvas.height = window.innerHeight;</p>
<p class="p1">}</p>
<p class="p1">resize();</p>
<p class="p1">window.addEventListener('resize', resize);</p>
<p class="p2"><br></p>
<p class="p1">app.addEventListener('mousemove', e =&gt; {</p>
<p class="p1"><span class="Apple-converted-space">  </span>mouse.x = e.clientX / window.innerWidth;</p>
<p class="p1"><span class="Apple-converted-space">  </span>mouse.y = e.clientY / window.innerHeight;</p>
<p class="p1">});</p>
<p class="p1">app.addEventListener('touchmove', e =&gt; {</p>
<p class="p1"><span class="Apple-converted-space">  </span>mouse.x = e.touches[0].clientX / window.innerWidth;</p>
<p class="p1"><span class="Apple-converted-space">  </span>mouse.y = e.touches[0].clientY / window.innerHeight;</p>
<p class="p1">}, {passive:true});</p>
<p class="p2"><br></p>
<p class="p1">function drawBg(s, alpha) {</p>
<p class="p1"><span class="Apple-converted-space">  </span>const W = canvas.width, H = canvas.height;</p>
<p class="p1"><span class="Apple-converted-space">  </span>const g = ctx.createLinearGradient(0, 0, W*0.7, H);</p>
<p class="p1"><span class="Apple-converted-space">  </span>g.addColorStop(0, s.bg[0]);</p>
<p class="p1"><span class="Apple-converted-space">  </span>g.addColorStop(0.5, s.bg[1]);</p>
<p class="p1"><span class="Apple-converted-space">  </span>g.addColorStop(1, s.bg[2]);</p>
<p class="p1"><span class="Apple-converted-space">  </span>ctx.globalAlpha = alpha;</p>
<p class="p1"><span class="Apple-converted-space">  </span>ctx.fillStyle = g;</p>
<p class="p1"><span class="Apple-converted-space">  </span>ctx.fillRect(0, 0, W, H);</p>
<p class="p1"><span class="Apple-converted-space">  </span>ctx.globalAlpha = 1;</p>
<p class="p1">}</p>
<p class="p2"><br></p>
<p class="p1">function spawnParticles(s) {</p>
<p class="p1"><span class="Apple-converted-space">  </span>const W = canvas.width, H = canvas.height;</p>
<p class="p1"><span class="Apple-converted-space">  </span>const p = s.particle;</p>
<p class="p1"><span class="Apple-converted-space">  </span>const mx = mouse.x * W, my = mouse.y * H;</p>
<p class="p1"><span class="Apple-converted-space">  </span>for(let i = 0; i &lt; p.count; i++){</p>
<p class="p1"><span class="Apple-converted-space">    </span>particles.push({</p>
<p class="p1"><span class="Apple-converted-space">      </span>x: mx + (Math.random()-0.5)*80,</p>
<p class="p1"><span class="Apple-converted-space">      </span>y: my + (Math.random()-0.5)*80,</p>
<p class="p1"><span class="Apple-converted-space">      </span>vx: p.vx(), vy: p.vy(),</p>
<p class="p1"><span class="Apple-converted-space">      </span>size: p.size(), color: p.color(),</p>
<p class="p1"><span class="Apple-converted-space">      </span>life: p.life, maxLife: p.life,</p>
<p class="p1"><span class="Apple-converted-space">      </span>grav: p.grav, drag: p.drag,</p>
<p class="p1"><span class="Apple-converted-space">      </span>rot: Math.random()*Math.PI*2,</p>
<p class="p1"><span class="Apple-converted-space">      </span>rotV: (Math.random()-0.5)*0.1</p>
<p class="p1"><span class="Apple-converted-space">    </span>});</p>
<p class="p1"><span class="Apple-converted-space">  </span>}</p>
<p class="p1"><span class="Apple-converted-space">  </span>if(particles.length &gt; 600) particles.splice(0, particles.length - 600);</p>
<p class="p1">}</p>
<p class="p2"><br></p>
<p class="p1">function drawPetal(x,y,size,rot,color,alpha) {</p>
<p class="p1"><span class="Apple-converted-space">  </span>ctx.save(); ctx.globalAlpha = alpha; ctx.translate(x,y); ctx.rotate(rot);</p>
<p class="p1"><span class="Apple-converted-space">  </span>ctx.fillStyle = color; ctx.beginPath();</p>
<p class="p1"><span class="Apple-converted-space">  </span>ctx.ellipse(0,-size*0.3,size*0.4,size*0.7,0,0,Math.PI*2);</p>
<p class="p1"><span class="Apple-converted-space">  </span>ctx.fill(); ctx.restore();</p>
<p class="p1">}</p>
<p class="p1">function drawSpark(x,y,size,rot,color,alpha) {</p>
<p class="p1"><span class="Apple-converted-space">  </span>ctx.save(); ctx.globalAlpha = alpha; ctx.translate(x,y);</p>
<p class="p1"><span class="Apple-converted-space">  </span>ctx.fillStyle = color; ctx.beginPath();</p>
<p class="p1"><span class="Apple-converted-space">  </span>ctx.arc(0,0,size*0.4,0,Math.PI*2);</p>
<p class="p1"><span class="Apple-converted-space">  </span>ctx.fill(); ctx.restore();</p>
<p class="p1">}</p>
<p class="p1">function drawLeaf(x,y,size,rot,color,alpha) {</p>
<p class="p1"><span class="Apple-converted-space">  </span>ctx.save(); ctx.globalAlpha = alpha; ctx.translate(x,y); ctx.rotate(rot);</p>
<p class="p1"><span class="Apple-converted-space">  </span>ctx.fillStyle = color; ctx.beginPath();</p>
<p class="p1"><span class="Apple-converted-space">  </span>ctx.ellipse(0,0,size*0.5,size,0,0,Math.PI*2);</p>
<p class="p1"><span class="Apple-converted-space">  </span>ctx.fill(); ctx.restore();</p>
<p class="p1">}</p>
<p class="p1">function drawSnow(x,y,size,rot,color,alpha) {</p>
<p class="p1"><span class="Apple-converted-space">  </span>ctx.save(); ctx.globalAlpha = alpha; ctx.translate(x,y);</p>
<p class="p1"><span class="Apple-converted-space">  </span>ctx.fillStyle = color; ctx.beginPath();</p>
<p class="p1"><span class="Apple-converted-space">  </span>ctx.arc(0,0,size*0.5,0,Math.PI*2);</p>
<p class="p1"><span class="Apple-converted-space">  </span>ctx.fill(); ctx.restore();</p>
<p class="p1">}</p>
<p class="p2"><br></p>
<p class="p1">const DRAW_FNS = [drawPetal, drawSpark, drawLeaf, drawSnow];</p>
<p class="p2"><br></p>
<p class="p1">function frame() {</p>
<p class="p1"><span class="Apple-converted-space">  </span>const W = canvas.width, H = canvas.height;</p>
<p class="p1"><span class="Apple-converted-space">  </span>ctx.clearRect(0,0,W,H);</p>
<p class="p1"><span class="Apple-converted-space">  </span>const s = SEASONS[cur];</p>
<p class="p1"><span class="Apple-converted-space">  </span>const sn = SEASONS[next];</p>
<p class="p1"><span class="Apple-converted-space">  </span>if(t &lt; 1) { drawBg(s, 1-t); drawBg(sn, t); } else { drawBg(s, 1); }</p>
<p class="p1"><span class="Apple-converted-space">  </span>if(t &lt; 1) t = Math.min(1, t + 0.025);</p>
<p class="p1"><span class="Apple-converted-space">  </span>spawnParticles(s);</p>
<p class="p1"><span class="Apple-converted-space">  </span>const drawFn = DRAW_FNS[cur];</p>
<p class="p1"><span class="Apple-converted-space">  </span>for(let i = particles.length-1; i &gt;= 0; i--){</p>
<p class="p1"><span class="Apple-converted-space">    </span>const p = particles[i];</p>
<p class="p1"><span class="Apple-converted-space">    </span>p.x += p.vx; p.y += p.vy;</p>
<p class="p1"><span class="Apple-converted-space">    </span>p.vy += p.grav; p.vx *= p.drag; p.vy *= p.drag;</p>
<p class="p1"><span class="Apple-converted-space">    </span>p.rot += p.rotV; p.life--;</p>
<p class="p1"><span class="Apple-converted-space">    </span>if(p.life&lt;=0||p.x&lt;-30||p.x&gt;W+30||p.y&lt;-30||p.y&gt;H+30){</p>
<p class="p1"><span class="Apple-converted-space">      </span>particles.splice(i,1); continue;</p>
<p class="p1"><span class="Apple-converted-space">    </span>}</p>
<p class="p1"><span class="Apple-converted-space">    </span>const alpha = Math.min(1, p.life/40) * Math.min(1,(p.maxLife-p.life)/10);</p>
<p class="p1"><span class="Apple-converted-space">    </span>drawFn(p.x, p.y, p.size, p.rot, p.color, alpha*0.85);</p>
<p class="p1"><span class="Apple-converted-space">  </span>}</p>
<p class="p1"><span class="Apple-converted-space">  </span>requestAnimationFrame(frame);</p>
<p class="p1">}</p>
<p class="p1">frame();</p>
<p class="p2"><br></p>
<p class="p1">document.querySelectorAll('.s-btn').forEach(btn =&gt; {</p>
<p class="p1"><span class="Apple-converted-space">  </span>btn.addEventListener('click', () =&gt; {</p>
<p class="p1"><span class="Apple-converted-space">    </span>const s = parseInt(btn.dataset.s);</p>
<p class="p1"><span class="Apple-converted-space">    </span>if(s === cur) return;</p>
<p class="p1"><span class="Apple-converted-space">    </span>next = s; t = 0; particles = []; cur = s;</p>
<p class="p1"><span class="Apple-converted-space">    </span>document.getElementById('season-title').textContent = SEASONS[s].name;</p>
<p class="p1"><span class="Apple-converted-space">    </span>document.getElementById('season-title').style.color = SEASONS[s].titleColor;</p>
<p class="p1"><span class="Apple-converted-space">    </span>document.getElementById('season-sub').textContent = SEASONS[s].sub;</p>
<p class="p1"><span class="Apple-converted-space">    </span>document.getElementById('season-sub').style.color = SEASONS[s].subColor;</p>
<p class="p1"><span class="Apple-converted-space">    </span>document.querySelectorAll('.s-btn').forEach(b =&gt; b.classList.remove('active'));</p>
<p class="p1"><span class="Apple-converted-space">    </span>btn.classList.add('active');</p>
<p class="p1"><span class="Apple-converted-space">  </span>});</p>
<p class="p1">});</p>
<p class="p2"><br></p>
<p class="p1">document.getElementById('season-title').style.color = SEASONS[0].titleColor;</p>
<p class="p1">document.getElementById('season-sub').style.color = SEASONS[0].subColor;</p>
<p class="p1">&lt;/script&gt;</p>
<p class="p1">&lt;/body&gt;</p>
<p class="p1">&lt;/html&gt;</p>
</body>
</html>
