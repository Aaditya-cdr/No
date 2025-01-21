#include <stdio.h>
#include <stdlib.h>
#include <time.h>

void numberGuessingGame() {
    int secretNumber, userGuess, attempts = 0;
    int lowerLimit = 1, upperLimit = 100; // Define the range of the number

    // Initialize random number generator
    srand(time(0));
    secretNumber = (rand() % (upperLimit - lowerLimit + 1)) + lowerLimit;

    printf("Welcome to the Number Guessing Game!\n");
    printf("I have selected a number between %d and %d.\n", lowerLimit, upperLimit);
    printf("Can you guess what it is?\n");

    // Game loop
    do {
        printf("Enter your guess: ");
        scanf("%d", &userGuess);
        attempts++;

        if (userGuess > secretNumber) {
            printf("Too high! Try again.\n");
        } else if (userGuess < secretNumber) {
            printf("Too low! Try again.\n");
        } else {
            printf("Congratulations! You guessed the number in %d attempts.\n", attempts);
        }
    } while (userGuess != secretNumber);

    printf("Thanks for playing!\n");
}

int main() {
    numberGuessingGame();
    return 0;
}
