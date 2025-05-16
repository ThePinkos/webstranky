<template>
  <header>
    <div>
      <a href="/"><span>Gymnázium, Veľká okružná 22, Žilina</span></a>
    </div>
    <nav>
      <a href="#oblasti">Oblasti</a>
      <a href="#archiv">Archív prác</a>
      <a href="#kontakt">Kontakt</a>
    </nav>
  </header>
  <div>
    <slot />
  </div>
  <footer>
    &copy; GVOZA tím,
    <a href="mailto:pekarova@gvoza.sk">pekarova@gvoza.sk</a>
  </footer>
</template>

<style scoped>
header {
  background-color: #004080;
  padding: 20px 60px;
  position: sticky;
  top: 0;

  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 20px;
  flex-wrap: wrap;
}

header span {
  color: #fff;
  font-size: 1.4rem;
  font-weight: 600;
  text-align: left;
}

header div a {
  text-decoration: none;
}

header img {
  margin-left: 10px;
  max-height: 50px;
}

header nav {
  display: flex;
  gap: 25px;
}

header nav a {
  font-size: 1.2rem;
  color: #fff;
  font-weight: bold;
  text-decoration: none;
  position: relative;
  transition: color 0.3s ease, transform 0.3s ease;
}

header nav a::after {
  content: "";
  position: absolute;
  left: 0;
  bottom: -5px;
  width: 0;
  height: 2px;
  background-color: #ffd700;
  transition: width 0.3s ease;
}

header nav a:hover {
  color: #ffd700;
}

header nav a:hover::after {
  width: 100%;
}

footer {
  background-color: #004080;
  color: white;
  text-align: center;
  padding: 20px 10px;
  font-size: 16px;
}

footer a {
  color: #ffd700;
  text-decoration: none;
}

footer a:hover {
  text-decoration: underline;
}
</style>
