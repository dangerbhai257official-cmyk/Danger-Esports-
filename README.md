<!doctype html>

<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>DANGER ESPORTS — APK Hub</title>
  <style>
    :root{
      --bg:#0b0f14; --card:#0f1720; --accent:#ff3b3b; --muted:#9aa4b2; --glass: rgba(255,255,255,0.03);
      --outline: 2px solid rgba(255,255,255,0.06);
      --radius:14px;
      font-family: Inter, ui-sans-serif, system-ui, -apple-system, 'Segoe UI', Roboto, 'Helvetica Neue', Arial;
    }
    *{box-sizing:border-box}
    html,body{height:100%;margin:0;background:linear-gradient(180deg,#071018 0%, #08121a 60%);color:#e6eef6}
    .container{max-width:1100px;margin:24px auto;padding:20px}
    header{display:flex;align-items:center;gap:16px;margin-bottom:20px}
    .logo{display:flex;align-items:center;gap:12px}
    .logo .mark{width:56px;height:56px;border-radius:12px;background:linear-gradient(135deg,var(--accent),#ff8a5b);display:flex;align-items:center;justify-content:center;font-weight:900;color:#071016;font-size:20px;box-shadow:0 6px 20px rgba(255,59,59,0.12)}
    h1{margin:0;font-size:20px;letter-spacing:1px}
    nav{margin-left:auto;display:flex;gap:8px}
    .btn{background:transparent;border:var(--outline);padding:8px 14px;border-radius:10px;color:var(--muted);font-weight:600;cursor:pointer;outline:none;display:inline-flex;align-items:center;gap:8px;backdrop-filter: blur(6px)}
    .btn:hover{transform:translateY(-4px);color:#fff}
    .btn:active{transform:translateY(0) scale(0.98)}
    .primary{border-color:rgba(255,59,59,0.18);box-shadow:0 6px 28px rgba(255,59,59,0.06);color:#fff}
    main{display:grid;grid-template-columns:1fr 360px;gap:18px}
    @media (max-width:900px){main{grid-template-columns:1fr}nav{display:none}}
    .card{background:linear-gradient(180deg, rgba(255,255,255,0.02), transparent);padding:18px;border-radius:var(--radius);border:1px solid rgba(255,255,255,0.03);box-shadow:0 8px 30px rgba(2,6,23,0.6)}
    .hero{display:flex;align-items:center;gap:18px}
    .hero .info h2{margin:0;font-size:20px}
    .hero .info p{margin:6px 0 0;color:var(--muted)}
    .search{display:flex;gap:8px;margin-top:14px}
    .search input{flex:1;padding:10px 12px;border-radius:10px;border:none;background:rgba(255,255,255,0.03);color:inherit}
    .upload-forms{display:flex;flex-direction:column;gap:12px;margin-top:14px}
    .file-list{margin-top:12px;display:grid;gap:10px}
    .file-item{display:flex;align-items:center;justify-content:space-between;padding:10px;border-radius:10px;background:var(--glass);border:1px solid rgba(255,255,255,0.02)}
    .file-item .meta{display:flex;align-items:center;gap:12px}
    .file-item .badge{font-size:12px;padding:6px 8px;border-radius:8px;background:rgba(255,255,255,0.02);border:1px solid rgba(255,255,255,0.03);color:var(--muted)}
    aside .card{position:sticky;top:22px}
    .gallery-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:8px}
    @media (max-width:480px){.gallery-grid{grid-template-columns:repeat(2,1fr)}}
    .thumb{width:100%;height:110px;object-fit:cover;border-radius:10px}
    .small{font-size:13px;color:var(--muted)}
    .controls{display:flex;gap:8px}
    .outline-btn{border:1px dashed rgba(255,255,255,0.04);padding:10px;border-radius:10px;cursor:pointer}
    .muted{color:var(--muted)}
    .route{display:none}
    .route.active{display:block}
    footer{margin-top:20px;text-align:center;color:var(--muted);font-size:12px}
    /* animated outline on buttons */
    .btn-outline{position:relative;overflow:hidden}
    .btn-outline::after{content:'';position:absolute;left:-120%;top:0;height:100%;width:120%;background:linear-gradient(90deg, transparent, rgba(255,255,255,0.03), transparent);transform:skewX(-15deg);transition:all .8s}
    .btn-outline:hover::after{left:120%}
    /* click ripple */
    .ripple{position:absolute;border-radius:50%;transform:scale(0);animation:ripple .6s linear;opacity:0.6;background:rgba(255,255,255,0.12)}
    @keyframes ripple{to{transform:scale(4);opacity:0}}
  </style>
</head>
<body>
  <div class="container">
    <header>
      <div class="logo">
        <div class="mark">DE</div>
        <div>
          <h1>DANGER ESPORTS</h1>
          <div class="small">APK Hub • Gaming theme • Mobile-friendly</div>
        </div>
      </div>
      <nav>
        <button class="btn btn-outline" data-route="home">Home</button>
        <button class="btn btn-outline" data-route="about">About</button>
        <button class="btn btn-outline" data-route="gallery">Gallery</button>
        <button class="btn primary" data-route="downloads">Downloads</button>
      </nav>
    </header><main>
  <section>
    <div id="home" class="card route active">
      <div class="hero">
        <div>
          <h2>Welcome to DANGER ESPORTS APK Hub</h2>
          <p class="small">Upload your APKs, make them discoverable on this site, and let users download directly. All files are stored locally in your browser (IndexedDB).</p>
        </div>
      </div>

      <div class="search card" style="margin-top:18px">
        <div style="display:flex;align-items:center;justify-content:space-between;gap:12px">
          <strong>Search APKs</strong>
          <div class="small muted">Type name and press Enter</div>
        </div>
        <div style="display:flex;gap:8px;margin-top:10px">
          <input id="searchInput" placeholder="Search APK name, e.g. FreeFire" />
          <button id="searchBtn" class="btn btn-outline">Search</button>
        </div>
        <div id="searchResults" class="file-list" style="margin-top:12px"></div>
      </div>

      <div class="card upload-forms">
        <strong>Upload APK (for users to download)</strong>
        <div class="small muted">Choose an .apk file. Files are kept locally in your browser so you can test downloads immediately.</div>
        <div style="display:flex;gap:8px;margin-top:8px;flex-wrap:wrap">
          <label class="btn btn-outline" style="cursor:pointer">
            Select APK
            <input id="apkInput" type="file" accept=".apk" style="display:none" />
          </label>
          <button id="addApkBtn" class="btn primary">Upload APK</button>
          <button id="clearApks" class="btn">Clear All APKs</button>
        </div>
        <div class="file-list" id="apkList"></div>
      </div>

    </div>

    <div id="about" class="card route">
      <h3>About DANGER ESPORTS</h3>
      <p class="small muted">This is a lightweight single-file demo for managing APK downloads and images. Built for DANGER ESPORTS — use it to share APKs with your community during testing. To host it publicly you will need a web server and real file storage (we can set that up later).</p>
      <div style="margin-top:12px;display:flex;gap:8px;flex-wrap:wrap">
        <button class="btn primary" id="openHostSteps">How to host online</button>
        <button class="btn" id="exportData">Export metadata (JSON)</button>
      </div>
    </div>

    <div id="gallery" class="card route">
      <h3>Gallery</h3>
      <div class="small muted">Upload images (screenshots, banners) and they'll appear below. Images stored locally in the browser.</div>
      <div style="display:flex;gap:8px;margin-top:12px">
        <label class="btn btn-outline" style="cursor:pointer">Select Images<input id="imgInput" type="file" accept="image/*" style="display:none" multiple></label>
        <button id="addImgBtn" class="btn primary">Upload Images</button>
        <button id="clearImgs" class="btn">Clear Gallery</button>
      </div>
      <div style="margin-top:14px" id="galleryGrid" class="gallery-grid"></div>
    </div>

    <div id="downloads" class="card route">
      <h3>Downloads</h3>
      <div class="small muted">All uploaded APKs are listed here. Users can search and click Download to save to their device.</div>
      <div style="margin-top:12px" id="downloadsList" class="file-list"></div>
    </div>
  </section>

  <aside>
    <div class="card">
      <strong>Quick actions</strong>
      <div style="margin-top:12px;display:flex;flex-direction:column;gap:8px">
        <button class="btn btn-outline" id="openDownloads">Open Downloads</button>
        <button class="btn" id="openGallery">Open Gallery</button>
        <button class="btn primary" id="openHome">Open Home</button>
      </div>

      <hr style="margin:14px 0;border:none;border-top:1px solid rgba(255,255,255,0.03)">
      <div class="small muted">Status</div>
      <div style="margin-top:8px;display:flex;gap:8px;align-items:center;justify-content:space-between">
        <div>APKs stored:</div><div id="countApks" class="badge">0</div>
      </div>
      <div style="margin-top:8px;display:flex;gap:8px;align-items:center;justify-content:space-between">
        <div>Images stored:</div><div id="countImgs" class="badge">0</div>
      </div>
    </div>
  </aside>
</main>

<footer>
  Built for <strong>DANGER ESPORTS</strong> — demo runs fully in your browser. To make files available to others online you will need hosting (I can help with that next).
</footer>

  </div>  <script>
    // --- tiny utility for button ripple ---
    document.addEventListener('click', function(e){
      const el = e.target.closest('.btn');
      if(!el) return;
      const r = document.createElement('span');
      r.className='ripple';
      const rect = el.getBoundingClientRect();
      const size = Math.max(rect.width, rect.height);
      r.style.width = r.style.height = size+'px';
      r.style.left = (e.clientX - rect.left - size/2)+'px';
      r.style.top = (e.clientY - rect.top - size/2)+'px';
      el.appendChild(r);
      setTimeout(()=> r.remove(),600);
    });

    // --- simple SPA routing ---
    document.querySelectorAll('[data-route]').forEach(btn=>btn.addEventListener('click', ()=>navigate(btn.dataset.route)));
    document.getElementById('openHome').addEventListener('click', ()=>navigate('home'));
    document.getElementById('openDownloads').addEventListener('click', ()=>navigate('downloads'));
    document.getElementById('openGallery').addEventListener('click', ()=>navigate('gallery'));

    function navigate(route){
      document.querySelectorAll('.route').forEach(r=>r.classList.remove('active'));
      document.getElementById(route).classList.add('active');
      window.scrollTo({top:0,behavior:'smooth'});
    }

    // --- IndexedDB wrapper ---
    const DB_NAME = 'danger-esports-db';
    const DB_VERSION = 1;
    let db;
    function openDB(){
      return new Promise((res,rej)=>{
        const rq = indexedDB.open(DB_NAME,DB_VERSION);
        rq.onupgradeneeded = e => {
          const idb = e.target.result;
          if(!idb.objectStoreNames.contains('files')) idb.createObjectStore('files',{keyPath:'id',autoIncrement:true});
          if(!idb.objectStoreNames.contains('images')) idb.createObjectStore('images',{keyPath:'id',autoIncrement:true});
        };
        rq.onsuccess = e => { db = e.target.result; res(db); };
        rq.onerror = e => rej(e);
      });
    }

    async function addFile(name,type,blob){
      const tx = db.transaction('files','readwrite');
      const s = tx.objectStore('files');
      return new Promise((res,rej)=>{
        const rq = s.add({name,type,blob,uploadedAt:Date.now()});
        rq.onsuccess = ()=>{tx.oncomplete = ()=>res();};
        rq.onerror = rej;
      });
    }
    async function getAllFiles(){
      return new Promise((res,rej)=>{
        const tx = db.transaction('files','readonly');
        const s = tx.objectStore('files');
        const rq = s.getAll(); rq.onsuccess = ()=>res(rq.result); rq.onerror=rej;
      });
    }
    async function clearFiles(){
      return new Promise((res,rej)=>{
        const tx = db.transaction('files','readwrite'); tx.objectStore('files').clear(); tx.oncomplete = ()=>res(); tx.onerror=rej;
      });
    }

    async function addImage(name,type,blob){
      const tx = db.transaction('images','readwrite'); const s = tx.objectStore('images');
      return new Promise((res,rej)=>{ const rq = s.add({name,type,blob,uploadedAt:Date.now()}); rq.onsuccess = ()=>{tx.oncomplete = ()=>res();}; rq.onerror = rej; });
    }
    async function getAllImages(){ return new Promise((res,rej)=>{ const tx = db.transaction('images','readonly'); const s = tx.objectStore('images'); const rq = s.getAll(); rq.onsuccess = ()=>res(rq.result); rq.onerror=rej; }); }
    async function clearImages(){ return new Promise((res,rej)=>{ const tx = db.transaction('images','readwrite'); tx.objectStore('images').clear(); tx.oncomplete = ()=>res(); tx.onerror=rej; }); }

    // --- UI bindings ---
    (async function init(){ await openDB(); await refreshCounts(); await renderAll(); })();

    const apkInput = document.getElementById('apkInput');
    const addApkBtn = document.getElementById('addApkBtn');
    const apkList = document.getElementById('apkList');
    const downloadsList = document.getElementById('downloadsList');
    const searchInput = document.getElementById('searchInput');
    const searchBtn = document.getElementById('searchBtn');
    const imgInput = document.getElementById('imgInput');
    const addImgBtn = document.getElementById('addImgBtn');
    const galleryGrid = document.getElementById('galleryGrid');
    const countApks = document.getElementById('countApks');
    const countImgs = document.getElementById('countImgs');
    const clearApks = document.getElementById('clearApks');
    const clearImgs = document.getElementById('clearImgs');
    const exportData = document.getElementById('exportData');
    const openHostSteps = document.getElementById('openHostSteps');

    addApkBtn.addEventListener('click', async ()=>{
      const f = apkInput.files && apkInput.files[0];
      if(!f){alert('Select an APK file first'); return}
      await addFile(f.name,f.type || 'application/vnd.android.package-archive',f);
      apkInput.value='';
      await renderApks(); await refreshCounts(); alert('APK uploaded to local DB — visible in Downloads');
    });

    addImgBtn.addEventListener('click', async ()=>{
      const files = Array.from(imgInput.files || []);
      if(files.length===0){alert('Select one or more images first'); return}
      for(const f of files) await addImage(f.name,f.type,f);
      imgInput.value=''; await renderGallery(); await refreshCounts();
    });

    clearApks.addEventListener('click', async ()=>{ if(confirm('Clear all stored APKs?')){ await clearFiles(); await renderApks(); await renderDownloads(); await refreshCounts(); } });
    clearImgs.addEventListener('click', async ()=>{ if(confirm('Clear all gallery images?')){ await clearImages(); await renderGallery(); await refreshCounts(); } });

    searchBtn.addEventListener('click', ()=>doSearch());
    searchInput.addEventListener('keydown', (e)=>{ if(e.key==='Enter') doSearch();});

    exportData.addEventListener('click', async ()=>{
      const files = await getAllFiles();
      const imgs = await getAllImages();
      const meta = {files: files.map(f=>({id:f.id,name:f.name,type:f.type,uploadedAt:f.uploadedAt})), images: imgs.map(i=>({id:i.id,name:i.name,uploadedAt:i.uploadedAt}))};
      const blob = new Blob([JSON.stringify(meta,null,2)],{type:'application/json'});
      const a = document.createElement('a'); a.href=URL.createObjectURL(blob); a.download='danger-esports-metadata.json'; a.click();
    });

    openHostSteps.addEventListener('click', ()=>{
      alert('Hosting steps:\n1) Get hosting (Netlify/Vercel/any VPS).\n2) Upload APK files to server or cloud storage and replace local-download links with server URLs.\n3) Use HTTPS.\nIf you want, I can prepare server-ready code next.');
    });

    async function doSearch(){ const q = (searchInput.value||'').trim().toLowerCase(); const list = await getAllFiles(); const res = list.filter(f=>f.name.toLowerCase().includes(q)); renderListTo(searchResults=document.getElementById('searchResults'),res); }

    async function renderAll(){ await renderApks(); await renderGallery(); await renderDownloads(); }

    async function renderApks(){ const files = await getAllFiles(); apkList.innerHTML=''; if(files.length===0){ apkList.innerHTML='<div class="small muted">No APKs uploaded yet.</div>'; } else { files.sort((a,b)=>b.uploadedAt-a.uploadedAt); for(const f of files){ const el = document.createElement('div'); el.className='file-item'; el.innerHTML = `<div class="meta"><div><strong>${escapeHtml(f.name)}</strong><div class="small muted">${new Date(f.uploadedAt).toLocaleString()}</div></div></div><div class="controls"><button class="btn btn-outline download-apk" data-id="${f.id}">Download</button><button class="btn" data-id="${f.id}">Remove</button></div>`; apkList.appendChild(el); }
      // bind events
      apkList.querySelectorAll('.download-apk').forEach(b=>b.addEventListener('click', async (ev)=>{const id=Number(ev.currentTarget.dataset.id); await downloadFileById(id);}));
      apkList.querySelectorAll('.btn[data-id]').forEach(b=>{ if(b.textContent.trim()==='Remove') b.addEventListener('click', async (ev)=>{const id=Number(ev.currentTarget.dataset.id); await removeFile(id); await renderApks(); await renderDownloads(); await refreshCounts(); }); });
    }
    }

    async function renderDownloads(){ const files = await getAllFiles(); downloadsList.innerHTML=''; if(files.length===0) downloadsList.innerHTML='<div class="small muted">No APKs available yet.</div>';
      else{ files.sort((a,b)=>b.uploadedAt-b.uploadedAt); renderListTo(downloadsList,files);
    }}

    function renderListTo(container, files){ container.innerHTML=''; if(files.length===0){container.innerHTML='<div class="small muted">No results</div>'; return}
      for(const f of files){ const row = document.createElement('div'); row.className='file-item'; const name = escapeHtml(f.name); row.innerHTML = `<div class="meta"><div><strong>${name}</strong><div class="small muted">${new Date(f.uploadedAt).toLocaleString()}</div></div></div><div class="controls"><button class="btn primary download-apk" data-id="${f.id}">Download</button></div>`; container.appendChild(row); }
      container.querySelectorAll('.download-apk').forEach(b=>b.addEventListener('click', async (ev)=>{const id=Number(ev.currentTarget.dataset.id); await downloadFileById(id);}));
    }

    async function removeFile(id){ return new Promise((res,rej)=>{ const tx = db.transaction('files','readwrite'); tx.objectStore('files').delete(id); tx.oncomplete = ()=>res(); tx.onerror=rej; }); }

    async function downloadFileById(id){ const tx = db.transaction('files','readonly'); const s = tx.objectStore('files'); const rq = s.get(id); rq.onsuccess = async ()=>{
      const rec = rq.result; if(!rec){alert('File not found'); return}
      const blob = rec.blob; // blob stored directly
      const a = document.createElement('a'); const url = URL.createObjectURL(blob); a.href = url; a.download = rec.name; document.body.appendChild(a); a.click(); a.remove(); setTimeout(()=>URL.revokeObjectURL(url), 60000);
    } }

    async function renderGallery(){ const imgs = await getAllImages(); galleryGrid.innerHTML=''; if(imgs.length===0) galleryGrid.innerHTML='<div class="small muted">No images uploaded yet.</div>';
      else{ imgs.sort((a,b)=>b.uploadedAt-a.uploadedAt); for(const img of imgs){ const url = URL.createObjectURL(img.blob); const d = document.createElement('div'); d.innerHTML = `<img src="${url}" class="thumb" alt="${escapeHtml(img.name)}"><div style="display:flex;justify-content:space-between;margin-top:6px"><div class="small">${escapeHtml(img.name)}</div><div class="controls"><button class="btn" data-id="${img.id}">Remove</button><a class="btn btn-outline" href="${url}" download="${img.name}">Save</a></div></div>`; galleryGrid.appendChild(d); }
        galleryGrid.querySelectorAll('.btn[data-id]').forEach(b=>b.addEventListener('click', async (ev)=>{ const id=Number(ev.currentTarget.dataset.id); const tx = db.transaction('images','readwrite'); tx.objectStore('images').delete(id); tx.oncomplete = async ()=>{ await renderGallery(); await refreshCounts(); }; }));
    }}

    async function refreshCounts(){ const files = await getAllFiles(); const imgs = await getAllImages(); countApks.textContent = files.length; countImgs.textContent = imgs.length; }

    // helpers
    function escapeHtml(s){ return String(s).replace(/[&<>"']/g,function(c){return{'&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;',"'":'&#39;'}[c];}); }

    // render initial lists
    async function renderAllOnLoad(){ await renderApks(); await renderDownloads(); await renderGallery(); }
    window.addEventListener('load', renderAllOnLoad);
  </script></body>
</html>
