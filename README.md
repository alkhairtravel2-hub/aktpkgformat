<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Umrah Package — Al Khair Travel</title>
  <style>
    :root{
      --bg:#0b1220;
      --card:#0f1724;
      --accent:#6ee7b7;
      --muted:#94a3b8;
      --glass: rgba(255,255,255,0.03);
      --glass2: rgba(255,255,255,0.02);
      --accent-2: #60a5fa;
      font-family: Inter, ui-sans-serif, system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial;
    }
    *{box-sizing:border-box}
    html,body{height:100%;}
    body{
      margin:0;
      background: linear-gradient(180deg,#071024 0%, #061226 60%);
      color:#e6eef8;
      padding:24px;
      -webkit-font-smoothing:antialiased;
      -moz-osx-font-smoothing:grayscale;
    }
    .wrap{
      max-width:980px;
      margin:0 auto;
      display:grid;
      grid-template-columns:1fr 420px;
      gap:20px;
    }
    header{
      grid-column:1/-1;
      display:flex;
      align-items:center;
      gap:12px;
      margin-bottom:6px;
    }
    header h1{
      font-size:20px;
      margin:0;
      letter-spacing:0.6px;
    }
    .card{
      background:linear-gradient(180deg,var(--card), #071A2B);
      border-radius:12px;
      padding:16px;
      box-shadow: 0 6px 20px rgba(2,6,23,0.6);
      border:1px solid rgba(255,255,255,0.03);
    }
    label{display:block;font-size:12px;color:var(--muted);margin-bottom:6px}
    textarea, input[type="text"], input[type="number"], input[type="tel"], input[type="email"]{
      width:100%;
      padding:10px 12px;
      border-radius:8px;
      border:1px solid rgba(255,255,255,0.04);
      background:var(--glass);
      color:inherit;
      outline:none;
      resize:vertical;
      font-size:14px;
    }
    .btn{
      display:inline-flex;
      align-items:center;
      gap:8px;
      padding:10px 12px;
      background:linear-gradient(90deg,var(--accent),var(--accent-2));
      color:#061226;
      border-radius:10px;
      font-weight:600;
      cursor:pointer;
      border:none;
      box-shadow: 0 6px 18px rgba(96,165,250,0.12);
      transition:transform .12s ease, box-shadow .12s ease;
    }
    .btn:hover{ transform:translateY(-3px) }
    .btn-ghost{
      background:transparent;
      color:var(--accent);
      border:1px solid rgba(110,231,183,0.12);
      box-shadow:none;
    }
    .controls{display:flex;gap:8px;flex-wrap:wrap}
    .preview{
      white-space:pre-wrap;
      font-family: "Segoe UI", Roboto, system-ui, sans-serif;
      background:linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));
      padding:14px;
      border-radius:10px;
      border:1px solid rgba(255,255,255,0.02);
      min-height:160px;
    }
    .section-row{display:flex;gap:10px;margin-bottom:10px}
    .section-row > *{flex:1}
    small.hint{display:block;color:var(--muted);margin-top:6px;font-size:12px}
    .footer-note{font-size:12px;color:var(--muted);margin-top:10px}
    .right-column{
      display:flex;
      flex-direction:column;
      gap:12px;
    }
    .field-grid{display:grid;grid-template-columns:1fr 1fr;gap:8px}
    .anim {
      transition: all .18s ease;
    }
    .anim:active { transform: scale(.99) }
    .logo{
      width:44px;height:44px;border-radius:8px;background:linear-gradient(135deg,var(--accent),var(--accent-2));
      display:flex;align-items:center;justify-content:center;font-weight:700;color:#051224;
      box-shadow:0 6px 18px rgba(0,0,0,0.3);
    }

    /* small screens */
    @media (max-width:960px){
      .wrap{grid-template-columns:1fr; padding-bottom:120px}
    }
  </style>
</head>
<body>
  <div class="wrap">
    <header>
      <div class="logo">AK</div>
      <div>
        <h1>Umrah Package  — Al Khair Travel UK</h1>
        <small class="hint">Paste raw data on the left → Click Here → Edit fields if needed → Generate</small>
      </div>
    </header>

    <!-- LEFT: RAW INPUT + PARSER -->
    <div class="card">
      <label for="rawInput">Raw data (paste here)</label>
      <textarea id="rawInput" rows="9" placeholder="Paste raw data exactly like your example...">
Makkah Hotel
Anjum Hotel 
Room Type: 
Check in and out : 15nov -20

Madina Hotel 
Room Type: 
Check in and out : 15nov -20 

Price £6561
      </textarea>

      <div style="height:10px"></div>

      <div class="controls">
        <button class="btn anim" id="parseBtn">Click Here</button>
        <button class="btn btn-ghost anim" id="clearBtn">Clear</button>
        <button class="btn btn-ghost anim" id="exampleBtn">Load Example</button>
      </div>

      <hr style="margin:14px 0;border:none;border-top:1px solid rgba(255,255,255,0.03)" />

      <label>Parsed / editable fields (click to edit)</label>

      <div style="margin-bottom:8px">
        <div class="section-row">
          <div>
            <label>Makkah Hotel name</label>
            <input id="makkahHotel" type="text" />
          </div>
          <div>
            <label>Makkah Room Type</label>
            <input id="makkahRoom" type="text" placeholder="Private Double, etc." />
          </div>
        </div>

        <div class="section-row">
          <div>
            <label>Makkah Check-In</label>
            <input id="makkahCin" type="text" placeholder="e.g. 17 Dec 2025 or 15nov" />
          </div>
          <div>
            <label>Makkah Check-Out</label>
            <input id="makkahCout" type="text" placeholder="e.g. 24 Dec 2025 or 20" />
          </div>
        </div>

        <div style="height:8px"></div>

        <div class="section-row">
          <div>
            <label>Madina Hotel name</label>
            <input id="madinaHotel" type="text" />
          </div>
          <div>
            <label>Madina Room Type</label>
            <input id="madinaRoom" type="text" />
          </div>
        </div>

        <div class="section-row">
          <div>
            <label>Madina Check-In</label>
            <input id="madinaCin" type="text" />
          </div>
          <div>
            <label>Madina Check-Out</label>
            <input id="madinaCout" type="text" />
          </div>
        </div>

        <div style="height:8px"></div>

        <div class="section-row">
          <div>
            <label>Price (total / raw)</label>
            <input id="priceRaw" type="text" />
            <small class="hint">You can paste "Price £6561" or "£6561" — parser will extract number.</small>
          </div>
          <div>
            <label>Per person cost (optional)</label>
            <input id="pricePer" type="text" placeholder="If blank, will attempt calculation" />
            <small class="hint">Leave blank to let script try to compute per-person (uses 1 or common divisor).</small>
          </div>
        </div>

      </div>
    </div>

    <!-- RIGHT: OUTPUT & CONTACT -->
    <div class="right-column">
      <div class="card">
        <label>Contact Info (appears in package)</label>
        <div class="field-grid">
          <input id="contactName" type="text" placeholder="Contact: Nadeem Altaf" value="Nadeem Altaf" />
          <input id="contactPhone" type="tel" placeholder="Direct Line# 020 3475 5753" value="020 3475 5753" />
        </div>
        <div style="height:8px"></div>
        <input id="contactEmail" type="email" placeholder="Email" value="nadeem@alkhairtravel.co.uk" />

        <div style="height:12px"></div>

        <div class="controls">
          <button class="btn anim" id="generateBtn">Generate Package</button>
          <button class="btn btn-ghost anim" id="copyBtn">Copy</button>
          <button class="btn btn-ghost anim" id="downloadBtn">Download .txt</button>
        </div>

        <div style="height:12px"></div>
        <label>Output Preview</label>
        <div id="output" class="preview"></div>
        <div class="footer-note">✔️ ATOL & ABTA protected – ATOL Number: <input id="atolNum" style="display:inline-block; width:150px; margin-left:6px; padding:6px 8px; border-radius:6px; border:1px solid rgba(255,255,255,0.03); background:transparent;" value="3853" /></div>
      </div>

      <div class="card">
        <label>Quick actions</label>
        <div style="display:flex;gap:8px;flex-wrap:wrap;margin-top:8px">
          <button id="formatWhats" class="btn anim btn-ghost">Format for WhatsApp</button>
          <button id="clearOutput" class="btn anim btn-ghost">Clear Output</button>
        </div>

        <div style="height:10px"></div>
        <small class="hint">The formatter tries to interpret short dates (like "15nov -20") and convert to readable dates (e.g. "15 Nov 2025"). If year is missing, the current year or next reasonable year will be used.</small>
      </div>
    </div>
  </div>

  <script>
    // Helper: month names map (short -> month index)
    const monthMap = {
      jan:0,feb:1,mar:2,apr:3,may:4,jun:5,jul:6,aug:7,sep:8,sept:8,oct:9,nov:10,dec:11
    };

    function parseRaw(raw){
      // Normalize
      const lines = raw.split(/\r?\n/).map(l => l.trim()).filter(l => l.length>0);
      const joined = lines.join("\n");

      // Basic extraction
      const makkah = {hotel:"", room:"", cin:"", cout:""};
      const madina = {hotel:"", room:"", cin:"", cout:""};
      let priceRaw = "";

      // Find Price
      const pMatch = joined.match(/price\s*[:\s]*£?\s*([\d,\.]+)/i) || joined.match(/£\s*([\d,\.]+)/);
      if(pMatch) priceRaw = "£" + pMatch[1].replace(/,/g,"");

      // find sections by headings
      // attempt to locate "Makkah" block and "Madina" block
      const makkahBlock = joined.split(/Madina\s*Hotel/i)[0] || joined;
      const madinaBlock = (joined.split(/Madina\s*Hotel/i)[1] || "");

      function extractBlock(block, target){
        // hotel name: line after heading or first line containing 'Hotel' phrase
        const lines = block.split(/\r?\n/).map(l=>l.trim()).filter(Boolean);
        // try to find a line that contains 'Makkah Hotel' or 'Madina Hotel' and take next non-empty line as hotel name
        for(let i=0;i<lines.length;i++){
          if(/makkah hotel/i.test(lines[i]) || /madina hotel/i.test(lines[i]) || /hotel/i.test(lines[i]) && i<3){
            // take next line if exists
            if(lines[i+1]) { target.hotel = lines[i+1]; break; }
          }
        }
        // fallback: first line if not set
        if(!target.hotel && lines[0]) target.hotel = lines[0].replace(/Hotel/i,"").trim();

        // Room Type
        const r = block.match(/room\s*type\s*[:\-]?\s*(.+)/i);
        if(r) target.room = r[1].trim();

        // Check in/out line - try multiple patterns
        const co = block.match(/check\s*(in|in\s*and\s*out|in\s*&\s*out|in\s*\/\s*out).*?:\s*(.+)/i)
                  || block.match(/check\s*in\s*[:\-]?\s*(.*?)\s*(?:-|to|–)\s*(.*)/i)
                  || block.match(/check\s*in\s*and\s*out\s*[:\-]?\s*(.+)/i)
                  || block.match(/check\s*in\s*and\s*out\s*[:\-]?\s*(\d+\w*)\s*(?:-|to|–)\s*(\d+\w*)/i);

        // generic pattern: e.g. "Check in and out : 15nov -20"
        const simple = block.match(/(\d{1,2}\s*[A-Za-z]{3,}\s*\d{0,4}?)\s*(?:-|to|–)\s*(\d{1,2}\s*[A-Za-z]{3,}?\s*\d{0,4}?)/i)
                      || block.match(/(\d{1,2}\w{3})\s*(?:-|to|–)\s*(\d{1,2}\w{0,3})/i);

        if(simple){
          target.cin = simple[1].trim();
          target.cout = simple[2].trim();
        } else if(co && co.length >= 3){
          target.cin = co[1] ? co[1].trim() : "";
          target.cout = co[2] ? co[2].trim() : "";
        } else {
          // last attempt: search for any two dates-like tokens in block
          const dates = block.match(/(\d{1,2}\s*[A-Za-z]{3,}\s*\d{0,4}?|\d{1,2}[A-Za-z]{3}|\d{1,2}\/\d{1,2}\/\d{2,4})/g);
          if(dates && dates.length>=2){
            target.cin = dates[0];
            target.cout = dates[1];
          }
        }
      }

      extractBlock(makkahBlock, makkah);
      extractBlock(madinaBlock, madina);

      return {makkah, madina, priceRaw};
    }

    function prettyDateFromTokens(token){
      if(!token) return "";
      token = token.replace(/\./g,"").trim();

      // if token contains '/', treat as numeric date (dd/mm/yyyy)
      if(/\d{1,2}\/\d{1,2}\/\d{2,4}/.test(token)){
        try{
          const parts = token.split("/");
          const d = parseInt(parts[0],10), m = parseInt(parts[1],10)-1, y = parts[2]?parseInt(parts[2],10):(new Date()).getFullYear();
          const dt = new Date(y,m,d);
          return formatHumanDate(dt);
        }catch(e){ return token }
      }

      // try to match: 15nov or 15 nov 2025 or 17 Dec 2025 or 20
      const m = token.match(/^(\d{1,2})\s*([A-Za-z]{3,})\s*(\d{2,4})?$/i)
              || token.match(/^(\d{1,2})\s*([A-Za-z]{3,})$/i)
              || token.match(/^(\d{1,2})\s*$/);

      const now = new Date();
      if(m){
        const day = parseInt(m[1],10);
        let mon = m[2] ? m[2].toLowerCase().slice(0,3) : null;
        let year = m[3] ? parseInt(m[3],10) : null;

        if(mon && monthMap[mon] !== undefined){
          const monIdx = monthMap[mon];
          if(!year){
            // choose year such that date is not in the distant past: prefer current year, unless that date is before today -> then next year
            year = now.getFullYear();
            const tentative = new Date(year, monIdx, day);
            if(tentative < new Date(now.getFullYear(), now.getMonth(), now.getDate()) && Math.abs(tentative - now) > 24*3600*1000){
              year = now.getFullYear() + 1;
            }
          }
          return formatHumanDate(new Date(year, monIdx, day));
        } else {
          // no month -> if only day number provided (e.g. "20"), we can't be sure which month.
          // We'll return day number and keep it simple: "20"
          if(!mon){
            return String(day);
          }
        }
      }

      // fallback: return token as-is
      return token;
    }

    function formatHumanDate(d){
      if(!d || !(d instanceof Date)) return "";
      const opts = { day: 'numeric', month: 'short', year:'numeric' };
      return new Intl.DateTimeFormat('en-GB', opts).format(d);
    }

    // UI wiring
    const rawInput = document.getElementById('rawInput');
    const parseBtn = document.getElementById('parseBtn');
    const clearBtn = document.getElementById('clearBtn');
    const exampleBtn = document.getElementById('exampleBtn');

    const makkahHotel = document.getElementById('makkahHotel');
    const makkahRoom = document.getElementById('makkahRoom');
    const makkahCin = document.getElementById('makkahCin');
    const makkahCout = document.getElementById('makkahCout');

    const madinaHotel = document.getElementById('madinaHotel');
    const madinaRoom = document.getElementById('madinaRoom');
    const madinaCin = document.getElementById('madinaCin');
    const madinaCout = document.getElementById('madinaCout');

    const priceRaw = document.getElementById('priceRaw');
    const pricePer = document.getElementById('pricePer');

    const contactName = document.getElementById('contactName');
    const contactPhone = document.getElementById('contactPhone');
    const contactEmail = document.getElementById('contactEmail');
    const atolNum = document.getElementById('atolNum');

    const generateBtn = document.getElementById('generateBtn');
    const outputEl = document.getElementById('output');
    const copyBtn = document.getElementById('copyBtn');
    const downloadBtn = document.getElementById('downloadBtn');
    const formatWhats = document.getElementById('formatWhats');
    const clearOutput = document.getElementById('clearOutput');

    parseBtn.addEventListener('click', ()=>{
      const parsed = parseRaw(rawInput.value || "");
      // populate fields
      makkahHotel.value = parsed.makkah.hotel || "";
      makkahRoom.value  = parsed.makkah.room || "";
      makkahCin.value   = parsed.makkah.cin || "";
      makkahCout.value  = parsed.makkah.cout || "";

      madinaHotel.value = parsed.madina.hotel || "";
      madinaRoom.value  = parsed.madina.room || "";
      madinaCin.value   = parsed.madina.cin || "";
      madinaCout.value  = parsed.madina.cout || "";

      priceRaw.value = parsed.priceRaw || "";
      // attempt to compute per person if price exists and pricePer empty
      if(priceRaw.value && !pricePer.value){
        // simple attempt: assume per person = price if <= 2000 or round/2/3/4 common divisors
        let n = parseFloat(parsed.priceRaw.replace(/[^0-9\.]/g,""));
        if(!isNaN(n)){
          // try find a sensible per-person (if n divisible by 2..6)
          let per = n;
          for(let k=1;k<=6;k++){
            if(n % k === 0 && n/k < 3000){
              per = n/k; break;
            }
          }
          pricePer.value = "£" + Math.round(per);
        }
      }
    });

    clearBtn.addEventListener('click', ()=>{
      rawInput.value = "";
    });

    exampleBtn.addEventListener('click', ()=>{
      rawInput.value = `Makkah Hotel
Anjum Hotel 
Room Type: Private Double
Check in and out : 17 Dec 2025 - 24 Dec 2025

Madina Hotel 
Pullman Madina
Room Type: Private Double
Check in and out : 24 Dec 2025 - 31 Dec 2025

Price £13250`;
    });

    function buildPackageText(opts){
      // opts contains values from inputs
      const p = [];
      p.push("🕋 *𝐔𝐌𝐑𝐀𝐇 𝐏𝐀𝐂𝐊𝐀𝐆𝐄*");
      // Per person cost
      const per = opts.pricePer || "";
      p.push("💷 𝐏𝐞𝐫 𝐩𝐞𝐫𝐬𝐨𝐧 𝐜𝐨𝐬𝐭: " + (per ? per : "£" + (opts.priceRaw ? parseFloat(opts.priceRaw.replace(/[^0-9\.]/g,"")) : "")));
      p.push("");
      p.push("🏨 *𝐇𝐨𝐭𝐞𝐥 𝐀𝐜𝐜𝐨𝐦𝐦𝐨𝐝𝐚𝐭𝐢𝐨𝐧*");
      p.push("");
      // Makkah section
      p.push("*𝐌𝐚𝐤𝐤𝐚𝐡 𝐇𝐨𝐭𝐞𝐥:*");
      p.push("*" + (opts.makkahHotel || "—") + "*");
      const mkCinPretty = prettyDateFromTokens(opts.makkahCin);
      const mkCoutPretty = prettyDateFromTokens(opts.makkahCout);
      if(mkCinPretty) p.push("📆 Check-In: " + mkCinPretty);
      if(mkCoutPretty) p.push("📆 Check-Out: " + mkCoutPretty);
      p.push("");
      // Madina
      p.push("*𝐌𝐚𝐝𝐢𝐧𝐚𝐡 𝐇𝐨𝐭𝐞𝐥:*");
      p.push("*" + (opts.madinaHotel || "—") + "*");
      const mdCinPretty = prettyDateFromTokens(opts.madinaCin);
      const mdCoutPretty = prettyDateFromTokens(opts.madinaCout);
      if(mdCinPretty) p.push("📆 Check-In: " + mdCinPretty);
      if(mdCoutPretty) p.push("📆 Check-Out: " + mdCoutPretty);
      p.push("");
      // Inclusions (kept generic)
      p.push("*𝐏𝐚𝐜𝐤𝐚𝐠𝐞 𝐈𝐧𝐜𝐥𝐮𝐬𝐢𝐨𝐧𝐬:*");
      p.push("• Visas are included");
      p.push("• Return FLight");
      p.push("• All Ground Transfer in Makkah & Madina");
      p.push("");
      // Contact
      p.push("*𝐂𝐨𝐧𝐭𝐚𝐜𝐭 𝐈𝐧𝐟𝐨𝐫𝐦𝐚𝐭𝐢𝐨𝐧:*");
      p.push("Contact: " + (opts.contactName || ""));
      p.push("Direct Line# " + (opts.contactPhone || ""));
      if(opts.contactEmail) p.push("Email: " + opts.contactEmail);
      p.push("");
      p.push("✔️ ATOL & ABTA protected – ATOL Number: " + (opts.atol || ""));
      p.push("");
      p.push('🕊 "The best of journeys are those that bring you closer to Allah."');
      p.push("");
      p.push("*Thank you*");
      return p.join("\n");
    }

    generateBtn.addEventListener('click', ()=>{
      const opts = {
        makkahHotel: makkahHotel.value.trim(),
        makkahRoom: makkahRoom.value.trim(),
        makkahCin: makkahCin.value.trim(),
        makkahCout: makkahCout.value.trim(),
        madinaHotel: madinaHotel.value.trim(),
        madinaRoom: madinaRoom.value.trim(),
        madinaCin: madinaCin.value.trim(),
        madinaCout: madinaCout.value.trim(),
        priceRaw: priceRaw.value.trim(),
        pricePer: pricePer.value.trim(),
        contactName: contactName.value.trim(),
        contactPhone: contactPhone.value.trim(),
        contactEmail: contactEmail.value.trim(),
        atol: atolNum.value.trim()
      };
      const out = buildPackageText(opts);
      outputEl.textContent = out;
    });

    copyBtn.addEventListener('click', async ()=>{
      const txt = outputEl.textContent || "";
      if(!txt) return alert("Nothing to copy — generate the package first.");
      try{
        await navigator.clipboard.writeText(txt);
        alert("Package copied to clipboard!");
      }catch(e){
        // fallback
        const ta = document.createElement('textarea');
        ta.value = txt; document.body.appendChild(ta);
        ta.select();
        document.execCommand('copy');
        ta.remove();
        alert("Copied (fallback)!");
      }
    });

    downloadBtn.addEventListener('click', ()=>{
      const txt = outputEl.textContent || "";
      if(!txt) return alert("Nothing to download — generate the package first.");
      const blob = new Blob([txt], {type:'text/plain;charset=utf-8'});
      const url = URL.createObjectURL(blob);
      const a = document.createElement('a');
      a.href = url; a.download = "umrah-package.txt"; document.body.appendChild(a);
      a.click(); a.remove(); URL.revokeObjectURL(url);
    });

    formatWhats.addEventListener('click', ()=>{
      if(!outputEl.textContent){ alert("Generate package first."); return; }
      // WhatsApp-friendly: remove surrounding asterisks (WhatsApp supports bold but user wanted star formatting earlier).
      // We'll convert markdown-like bold to WhatsApp bold (same '*') and keep as-is.
      // Provide a trimmed copy for WhatsApp by ensuring line breaks and small changes.
      const txt = outputEl.textContent;
      // open a new small window with the text so user can copy easily
      const w = window.open("", "_blank", "width=600,height=600");
      if(w){
        w.document.write("<pre style='font-family:Segoe UI,Roboto,Arial;padding:16px;background:#071123;color:#fff;white-space:pre-wrap;'>"+escapeHtml(txt)+"</pre>");
        w.document.title = "WhatsApp copy";
      } else {
        alert("Popup blocked — allow popups for this site to use the WhatsApp preview.");
      }
    });

    clearOutput.addEventListener('click', ()=>{
      outputEl.textContent = "";
    });

    function escapeHtml(s){
      return s.replace(/&/g,"&amp;").replace(/</g,"&lt;").replace(/>/g,"&gt;");
    }

    // parse on load
    window.addEventListener('load', ()=>{ parseBtn.click(); });

  </script>
</body>
</html>
