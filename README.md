<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>MN Portfolio — Task 4</title>
  <style>
    :root{
      --bg:#0f1724; --card:#0b1220; --accent:#6ee7b7; --text:#e6eef6; --muted:#9fb4c8;
      font-family:Inter, system-ui, Arial;
    }
    *{box-sizing:border-box; margin:0; padding:0}
    body{background:var(--bg); color:var(--text); line-height:1.5}
    .container{max-width:1100px; margin:auto; padding:1rem}
    header{display:flex;justify-content:space-between;align-items:center;position:sticky;top:0;padding:1rem;background:rgba(15,23,36,0.9);backdrop-filter:blur(8px);z-index:100}
    .logo{font-weight:700;color:var(--accent);text-decoration:none;font-size:1.3rem}
    nav{display:flex;gap:1rem}
    nav a{color:var(--muted);text-decoration:none;padding:0.5rem;border-radius:6px}
    nav a:hover{background:rgba(255,255,255,0.05);color:var(--text)}
    .btn{display:inline-block;background:var(--accent);color:#022;padding:.6rem 1rem;border-radius:8px;font-weight:600;text-decoration:none;margin-top:.5rem}
    section{margin-top:2rem}
    h1,h2,h3,h4{margin-bottom:.5rem}
    .skill-list{list-style:none;display:flex;gap:.6rem;flex-wrap:wrap;margin-top:.5rem}
    .skill-list li{background:rgba(255,255,255,0.04);padding:.4rem .6rem;border-radius:8px}
    footer{text-align:center;padding:1rem;margin-top:2rem;color:var(--muted);border-top:1px solid rgba(255,255,255,0.05)}
    /* ToDo styles */
    #todoApp{background:var(--card);padding:1rem;border-radius:10px;margin-top:1rem}
    #taskForm{display:flex;gap:.5rem;margin-bottom:1rem}
    #taskForm input{flex:1;padding:.6rem;border-radius:8px;border:none}
    #taskForm button{padding:.6rem .9rem;border-radius:8px;border:none;background:var(--accent);color:#022;font-weight:600}
    #list{list-style:none;padding:0;margin:0}
    #list li{display:flex;align-items:center;gap:.5rem;padding:.5rem;background:rgba(255,255,255,0.04);margin-bottom:.4rem;border-radius:6px}
    #list li.completed{text-decoration:line-through;opacity:.6}
    /* Product styles */
    #products{background:var(--card);padding:1rem;border-radius:10px;margin-top:1rem}
    .wrap{display:grid;grid-template-columns:280px 1fr;gap:1rem}
    .panel{background:rgba(255,255,255,0.02);padding:1rem;border-radius:8px}
    .products-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(220px,1fr));gap:1rem}
    .card{background:rgba(255,255,255,0.03);padding:1rem;border-radius:10px}
    @media(max-width:800px){.wrap{grid-template-columns:1fr}nav{display:none}#navToggle{display:block}}
    #navToggle{display:none;background:none;border:none;color:var(--text);font-size:1.5rem}
  </style>
</head>
<body>
  <header class="container">
    <a href="#home" class="logo">MN</a>
    <button id="navToggle">☰</button>
    <nav id="mainNav">
      <a href="#home">Home</a>
      <a href="#about">About</a>
      <a href="#projects">Projects</a>
      <a href="#todo">To-Do</a>
      <a href="#products">Products</a>
      <a href="#contact">Contact</a>
    </nav>
  </header>

  <section id="home" class="container">
    <h1>Hi, I’m MN 👋</h1>
    <p>Web Developer Intern @ Apex Planet | Building interactive, responsive websites.</p>
    <a href="#projects" class="btn">View My Projects</a>
  </section>

  <section id="about" class="container">
    <h2>About Me</h2>
    <p>I’m passionate about web development and skilled in HTML, CSS, JS, and building functional apps.</p>
    <ul class="skill-list">
      <li>HTML5 & CSS3</li>
      <li>JavaScript (ES6+)</li>
      <li>Responsive Design</li>
      <li>LocalStorage</li>
    </ul>
  </section>

  <section id="projects" class="container">
    <h2>Projects</h2>
    <ul>
      <li><a href="#todo">To-Do App</a> — Save, edit, and manage tasks locally.</li>
      <li><a href="#products">Product Listing</a> — Filter, sort, and search products.</li>
    </ul>
  </section>

  <section id="todo" class="container">
    <h2>To-Do App</h2>
    <div id="todoApp">
      <form id="taskForm">
        <input id="text" type="text" placeholder="Add new task..." required />
        <button>Add</button>
      </form>
      <ul id="list"></ul>
      <div style="margin-top:.5rem">
        <button id="clearDone">Clear Completed</button>
        <button id="clearAll">Clear All</button>
      </div>
    </div>
  </section>

  <section id="products" class="container">
    <h2>Product Listing</h2>
    <div class="wrap">
      <aside class="panel">
        <input id="search" placeholder="Search products..." />
        <label>Category:
          <select id="category"><option value="all">All</option></select>
        </label>
        <label>Max Price:
          <input id="priceMax" type="number" min="0" placeholder="No limit" />
        </label>
        <label>Sort by:
          <select id="sort">
            <option value="default">Default</option>
            <option value="price-asc">Price: Low → High</option>
            <option value="price-desc">Price: High → Low</option>
            <option value="rating-desc">Rating: High → Low</option>
            <option value="name-asc">Name A → Z</option>
          </select>
        </label>
        <button id="reset">Reset</button>
      </aside>
      <main>
        <div class="panel">Showing <strong id="n"></strong> products</div>
        <div id="grid" class="products-grid"></div>
      </main>
    </div>
  </section>

  <section id="contact" class="container">
    <h2>Contact Me</h2>
    <form id="contactForm">
      <label>Name <input type="text" required /></label>
      <label>Email <input type="email" required /></label>
      <label>Message <textarea rows="5" required></textarea></label>
      <button type="submit" class="btn">Send</button>
    </form>
  </section>

  <footer>
    <small>© <span id="year"></span> MN | Built with HTML, CSS & JS</small>
  </footer>

  <script>
    // Navbar toggle
    document.getElementById('navToggle').addEventListener('click',()=>{
      const nav=document.getElementById('mainNav');
      nav.style.display=nav.style.display==='flex'?'none':'flex';
    });
    document.getElementById('year').textContent=new Date().getFullYear();

    // ToDo App
    const listEl=document.getElementById('list');
    const form=document.getElementById('taskForm');
    const text=document.getElementById('text');
    const STORAGE_KEY='mn_tasks_v1';
    let tasks=JSON.parse(localStorage.getItem(STORAGE_KEY)||'[]');

    function save(){localStorage.setItem(STORAGE_KEY,JSON.stringify(tasks));}
    function render(){listEl.innerHTML='';tasks.forEach(task=>{
      const li=document.createElement('li');if(task.done)li.classList.add('completed');
      const chk=document.createElement('input');chk.type='checkbox';chk.checked=task.done;
      chk.addEventListener('change',()=>{task.done=chk.checked;save();render();});
      const span=document.createElement('span');span.textContent=task.text;
      span.addEventListener('dblclick',()=>{const newText=prompt('Edit task',task.text);
        if(newText){task.text=newText.trim();save();render();}});
      const del=document.createElement('button');del.textContent='Delete';
      del.addEventListener('click',()=>{tasks=tasks.filter(t=>t.id!==task.id);save();render();});
      li.append(chk,span,del);listEl.append(li);
    });}
    form.addEventListener('submit',e=>{e.preventDefault();
      if(!text.value.trim())return;
      tasks.unshift({id:Date.now(),text:text.value.trim(),done:false});
      text.value='';save();render();});
    document.getElementById('clearDone').addEventListener('click',()=>{tasks=tasks.filter(t=>!t.done);save();render();});
    document.getElementById('clearAll').addEventListener('click',()=>{if(confirm('Clear all tasks?')){tasks=[];save();render();}});
    render();

    // Products
    const products=[
      {id:1,name:'Classic Tee',category:'Clothing',price:399,rating:4.5},
      {id:2,name:'Sport Sneakers',category:'Footwear',price:2499,rating:4.7},
      {id:3,name:'Leather Belt',category:'Accessories',price:799,rating:4.1},
      {id:4,name:'Summer Hat',category:'Accessories',price:399,rating:4.0},
      {id:5,name:'Jeans Slim',category:'Clothing',price:1299,rating:4.3},
      {id:6,name:'Running Socks',category:'Footwear',price:199,rating:4.2},
      {id:7,name:'Hoodie',category:'Clothing',price:1599,rating:4.6},
      {id:8,name:'Sandals',category:'Footwear',price:699,rating:4.0}
    ];
    const grid=document.getElementById('grid');
    const cat=document.getElementById('category');
    const priceMax=document.getElementById('priceMax');
    const sort=document.getElementById('sort');
    const search=document.getElementById('search');
    const nEl=document.getElementById('n');
    const categories=[...new Set(products.map(p=>p.category))];
    categories.forEach(c=>{const o=document.createElement('option');o.value=c;o.textContent=c;cat.append(o);});

    function renderProducts(list){grid.innerHTML='';nEl.textContent=list.length;
      if(!list.length){grid.innerHTML='<p>No products found</p>';return;}
      list.forEach(p=>{
        const card=document.createElement('div');card.className='card';
        card.innerHTML=`<h4>${p.name}</h4><p>${p.category} • ⭐ ${p.rating}</p><p><b>₹${p.price}</b></p>`;
        grid.append(card);
      });
    }
    function applyFilters(){
      let out=[...products];
      const q=search.value.toLowerCase();
      if(q)out=out.filter(p=>p.name.toLowerCase().includes(q)||p.category.toLowerCase().includes(q));
      if(cat.value!=='all')out=out.filter(p=>p.category===cat.value);
      const max=parseFloat(priceMax.value);
      if(!isNaN(max))out=out.filter(p=>p.price<=max);
      switch(sort.value){
        case'price-asc':out.sort((a,b)=>a.price-b.price);break;
        case'price-desc':out.sort((a,b)=>b.price-a.price);break;
        case'rating-desc':out.sort((a,b)=>b.rating-a.rating);break;
        case'name-asc':out.sort((a,b)=>a.name.localeCompare(b.name));break;
      }
      renderProducts(out);
    }
    [search,cat,priceMax,sort].forEach(el=>el.addEventListener('input',applyFilters));
    document.getElementById('reset').addEventListener('click',()=>{search.value='';cat.value='all';priceMax.value='';sort.value='default';applyFilters();});
    applyFilters();

    // Contact form demo
    document.getElementById('contactForm').addEventListener('submit',e=>{e.preventDefault();alert('Demo: form would submit here.');e.target.reset();});
  </script>
</body>
</html>
