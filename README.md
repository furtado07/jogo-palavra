# jogo-palavralet palavra;

function setup() {
  createCanvas(900, 900);

  palavra = palavraAleatoria();
  
}

function palavraAleatoria() {
  
  let palavras = ["John Deere", "New Holland", "Valtra"];
  
  return random(palavras);
}

function inicializaCores() {
  background("blue");
  fill("white");
  textSize(100);
  textAlign(CENTER, CENTER);
}

function palavraParcial(minimo, maximo) {
  let quantidade = map(mouseX, minimo, maximo, 1, palavra.length);
  let parcial = palavra.substring(0, quantidade);
  return parcial;
}

function draw() {
  
  inicializaCores();

  let texto = palavraParcial(0, width);
    
  text(texto, 400, 400);
  
}

function modoNoturno(horario) {
  if (horario > 18) {
    console.log("Você precisa ligar o modo escuro!");
  } else {
    console.log("Modo noturno não é necessário neste momento.");
  }
}

modoNoturno(15);
modoNoturno(20);

