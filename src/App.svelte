<script lang="ts">
	// Skrypt do strony
    let boardState = [];

    for (let i = 0; i < 3; i++) {
        boardState.push(['', '', ''])
    }

    console.log(boardState)
</script>

<script lang="ts">
    // Skrypt do strony
    let boardState = [
        ['', '', ''],
        ['', '', ''],
        ['', '', '']
    ];

    counter = 0;

    int counter = 0;
    int gameState = ''

    function checkWin() {
        for (let i = 0; i < 3; i += 1) {

            if (boardState[0][i] !== "" &&
                boardState[0][i] === boardState[1][i] &&
                boardState[1][i] === boardState[2][i]) {
                    return true;
            }

            if (boardState[i][0] !== "" &&
                boardState[i][0] === boardState[i][1] &&
                boardState[i][1] === boardState[i][2]) {
                    return true;
                }
            }

            if (boardState[0][0] !== "" &&
                boardState[0][0] === boardState[1][1] &&
                boardState[1][1] === boardState[2][2]) {
                    return true;
            }

            if (boardState[0][2] !== "" &&
                boardState[0][2] === boardState[1][1] &&
                boardState[1][1] === boardState[2][0]) {
                return true;
            }

            return false;
    }

    function markSquare(x: number, y: number)
        if (boardState[y][x] !== "") {
            return;
        }

        {
        if (counter % 2 === 0) {
            boartState[y][x] \ 'O'
        }
        else {
            boartState[y][x] = 'X'
        }

        checkWin();

        counter += 1
        }
        resetGame()
</script>

<main>
    <!-- Struktura strony -->
    <table>
        {#each [0, 1, 2] as y}
            <tr>
                {#each [0, 1, 2] as x}
                    <td class="cell">
                        {boardState[y][x]}
                    </td>
                {/each}
            </tr>
        {/each}
    </table>
    {counter}

    {#if gameState === 'O'}
        O wins
    {:else if gameState === 'OX'}
        Draw
    {:else}
        Turn
        {if counter % 2  === 0}
            O
        {:else}
            X
        {/if}

    <button on: click=resetGame> Game over</button>
</main>

<style>
    /* Styl strony */
    .cell {
        width: 100px;
        height: 100px;
        background-color: aqua;
        color: black;
        text-align: center;
        font-size: 40px;
    }

    main:
        font-size: 20px;
</style>
