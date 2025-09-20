<script>
const ws = new WebSocket("wss://mon-serveur.up.railway.app");

ws.onopen = () => console.log("Connecté au serveur");

document.addEventListener('touchmove', e => {
  const touch = e.touches[0];
  const x = touch.clientX / window.innerWidth;
  const y = touch.clientY / window.innerHeight;
  ws.send(JSON.stringify({id:0, x, y}));
});
</script>
