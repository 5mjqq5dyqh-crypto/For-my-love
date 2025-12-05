# For-my-love
<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width,initial-scale=1" />
<title>carta para mi pinchecha</title>
<style>
  :root{--bg:#0b0b0d;--card:#fefefe;--accent:#ff4f9a;--paper:#fff7fb}
  html,body{height:100%;margin:0;font-family:system-ui,-apple-system,Segoe UI,Roboto,Arial;}
  body{background:linear-gradient(180deg,#071026 0%, #0b0b0d 100%);display:flex;align-items:center;justify-content:center;padding:24px;color:#111}
  .wrap{max-width:480px;width:100%;display:flex;flex-direction:column;align-items:center;gap:20px}
  .hint{color:#cbd5e1;font-size:14px;text-align:center}
  /* card */
  .scene{perspective:1200px;width:100%;max-width:420px;height:300px}
  .card{
    width:100%;height:100%;border-radius:16px;cursor:pointer;position:relative;
    transform-style:preserve-3d;transition:transform 700ms cubic-bezier(.2,.9,.3,1);
  }
  .card.open{transform:rotateY(180deg)}
  .side{
    position:absolute;inset:0;border-radius:16px;backface-visibility:hidden;overflow:hidden;
    box-shadow:0 10px 30px rgba(2,6,23,.6);
  }
  /* front (sobre cerrado) */
  .front{background:linear-gradient(180deg,#fde8f6,#ffdfee);display:flex;align-items:center;justify-content:center;padding:20px}
  .envelope{
    width:86%;height:68%;background:linear-gradient(180deg,#fff,#ffeef8);border-radius:12px;position:relative;
    box-shadow:0 6px 16px rgba(0,0,0,.25);
  }
  .flap{
    position:absolute;left:0;right:0;top:0;height:52%;background:linear-gradient(180deg,#ff4f9a,#ff79b8);
    clip-path: polygon(0 0, 50% 72%, 100% 0, 100% 100%, 0 100%);
    display:flex;align-items:flex-end;justify-content:center;color:white;font-weight:700;padding-bottom:10px;
    font-size:16px;
  }
  .paper-edge{
    position:absolute;left:7%;right:7%;top:20%;height:60%;background:linear-gradient(180deg,#fff,#fff7fb);border-radius:6px;
    display:flex;align-items:center;justify-content:center;color:#ff4f9a;font-weight:700;
  }
  /* back (carta abierta) */
  .back{transform:rotateY(180deg);background:linear-gradient(180deg,#fff8fb,#fff4f9);padding:24px;display:flex;flex-direction:column;align-items:center;justify-content:center}
  .letter{
    width:100%;height:100%;background:var(--paper);border-radius:12px;padding:18px;box-sizing:border-box;
    box-shadow:inset 0 1px 0 rgba(0,0,0,.02);
    overflow:auto;color:#111;font-size:16px;line-height:1.5;
    -webkit-overflow-scrolling:touch;
  }
  .small{font-size:13px;color:#475569;margin-top:10px;text-align:center}
  .tap{margin-top:8px;background:transparent;border:2px dashed rgba(7,10,25,.06);padding:8px;border-radius:8px;color:#475569}
  /* responsive */
  @media (max-width:420px){
    .scene{height:320px}
    .letter{font-size:15px}
  }
</style>
</head>
<body>
  <div class="wrap">
    <div class="scene" role="button" aria-label="tocar para abrir la carta">
      <div id="card" class="card" onclick="toggleCard()">
        <div class="side front" aria-hidden="false">
          <div class="envelope">
            <div class="flap">para mi pinchecha</div>
            <div class="paper-edge">toca para abrir</div>
          </div>
        </div>
        <div class="side back" aria-hidden="true">
          <div class="letter" id="letter">
mi pinchecha quiero que sepas algo que a veces no digo pero siempre siento
tú llegaste a mi vida y desde ese momento todo se siente más bonito más tranquilo y más completo
me haces reír me haces sentir querido y sin darte cuenta te convertiste en mi lugar seguro
no necesito que seas perfecta porque con todo lo que eres ya me haces feliz
te quiero tanto que a veces no encuentro palabras para explicarlo pero créeme que cada día te quiero un poquito más
          </div>
        </div>
      </div>
    </div>
    <div class="hint">toca la carta para que se abra y muestre la carta</div>
    <div class="small">si quieres que cambie algo dentro de la carta dimelo y lo actualizo</div>
  </div>

<script>
function toggleCard(){
  const c = document.getElementById('card');
  c.classList.toggle('open');
}
</script>
</body>
</html>
