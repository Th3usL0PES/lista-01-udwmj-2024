
Jogo: Pedra, papel e tesoura em JAVASCRIPT 


// Função para gerar um número aleatório entre 0 e 2

function getRandomChoice() {
  return Math.floor(Math.random() * 3);
}

// Função para converter o número aleatório em uma escolha (pedra, papel ou tesoura)

function getComputerChoice() {
  switch (getRandomChoice()) {
    case 0:
      return "pedra";
    case 1:
      return "papel";
    case 2:
      return "tesoura";
  }
}

// Função para determinar quem ganhou

function getWinner(userChoice, computerChoice) {
  if (userChoice === computerChoice) {
    return "Empate!";
  } else if (
    (userChoice === "pedra" && computerChoice === "tesoura") ||
    (userChoice === "papel" && computerChoice === "pedra") ||
    (userChoice === "tesoura" && computerChoice === "papel")
  ) {
    return "Você ganhou!";
  } else {
    return "O computador ganhou!";
  }
}

// Função principal do jogo

function playGame() {
  var userChoice = prompt("Escolha pedra, papel ou tesoura:");
  userChoice = userChoice.toLowerCase();
  var computerChoice = getComputerChoice();
  alert("Você escolheu: " + userChoice);
  alert("O computador escolheu: " + computerChoice);
  alert(getWinner(userChoice, computerChoice));
}

// Iniciar o jogo

playGame();



////////////////////////////////////////////////////////////////////////////////////


Jogo: Pedra, papel e tesoura em PHP

<?php
// Função para determinar o vencedor
function determinarVencedor($jogador, $computador) {
    if ($jogador === $computador) {
        return "Empate!";
    }

    if (($jogador === "pedra" && $computador === "tesoura") ||
        ($jogador === "papel" && $computador === "pedra") ||
        ($jogador === "tesoura" && $computador === "papel")) {
        return "Você venceu!";
    } else {
        return "Você perdeu!";
    }
}

// Jogada do jogador
$jogador = strtolower(readline("Escolha pedra, papel ou tesoura: "));

// Jogada do computador
$opcoes = ["pedra", "papel", "tesoura"];
$computador = $opcoes[array_rand($opcoes)];

echo "Você escolheu: $jogador\n";
echo "O computador escolheu: $computador\n";

// Determinar o vencedor
$resultado = determinarVencedor($jogador, $computador);
echo $resultado;
?>


