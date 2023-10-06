fun imprimirTabuleiro(tabuleiro: Array<Array<String>>) {
    for (linha in tabuleiro) {
        println(linha.joinToString(" | "))
        println("-".repeat(9))
    }
}

fun verificarVitoria(tabuleiro: Array<Array<String>>, jogador: String): Boolean {
    for (linha in tabuleiro) {
        if (linha.all { it == jogador }) {
            return true
        }
    }

    for (coluna in 0 until 3) {
        if ((0 until 3).all { tabuleiro[it][coluna] == jogador }) {
            return true
        }
    }

    if ((0 until 3).all { tabuleiro[it][it] == jogador } ||
        (0 until 3).all { tabuleiro[it][2 - it] == jogador }
    ) {
        return true
    }

    return false
}

fun jogarJogoDaVelha() {
    val tabuleiro = Array(3) { Array(3) { " " } }
    var jogadorAtual = "X"
    var jogoAcabou = false

    while (!jogoAcabou) {
        imprimirTabuleiro(tabuleiro)
        println("É a vez do jogador $jogadorAtual")
        print("Escolha a linha (0, 1, 2): ")
        val linha = readLine()!!.toInt()
        print("Escolha a coluna (0, 1, 2): ")
        val coluna = readLine()!!.toInt()

        if (tabuleiro[linha][coluna] == " ") {
            tabuleiro[linha][coluna] = jogadorAtual

            if (verificarVitoria(tabuleiro, jogadorAtual)) {
                imprimirTabuleiro(tabuleiro)
                println("Jogador $jogadorAtual venceu!")
                jogoAcabou = true
            } else {
                jogadorAtual = "O"
            }
        } else {
            println("Essa posição já está ocupada. Tente novamente.")
        }
    }

    println("Fim do jogo!")
}

fun main() {
    jogarJogoDaVelha()
}
