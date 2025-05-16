<template>
  <div>
    <h2 id="oblasti">Oblasti, v ktorých môžeš sútažiť:</h2>

    <div class="oblasti">
      <div>Matematika, fyzika</div>
      <div>Chémia, potravinárstvo</div>
      <div>Biológia</div>
      <div>Životné prostredie, geografia, geológia</div>
      <div>Informatika</div>
      <div>Elektrotechnika a hardware</div>
      <div>História, filozofia, právne vedy</div>
      <div>Teória kultúry, umenie, umelecká, odevná tvorba</div>
      <div>Ekonomika a riadenie</div>
      <div>Pedagogika, psychológia, sociológia</div>
      <div>Tvorba učebných pomôcok, didaktické technológie</div>
      <div>Problematika voľného času</div>
      <div>Zdravotníctvo a farmakológia</div>
      <div>
        Pôdohospodárstvo (poľnohospodárstvo, lesné a vodné hospodárstvo)
      </div>
      <div>Cestovný ruch, hotediverstvo, gastronómia</div>
      <div>Strojárstvo, hutníctvo, doprava</div>
      <div>Stavebníctvo, geodézia, kartografia</div>
    </div>
  </div>
</template>

<style scoped>
.oblasti {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  margin: 0 auto;
  max-width: 1300px;
  padding: 0px 20px 30px 20px;
  gap: 20px;
}

.oblasti div {
  background: linear-gradient(135deg, #deeeff, #aed7ff);
  border-radius: 12px;
  padding: 20px;
  width: 230px;
  text-align: center;
  font-weight: bold;
  color: #003366;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);

  display: flex;
  align-items: center;
  justify-content: center;
}
</style>
