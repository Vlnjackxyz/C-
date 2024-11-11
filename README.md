#include <iostream>
#include <cstdlib>  // For rand() and srand()
#include <ctime>    // For time()

int main() {
    int number, guess, attempts = 0;
    int lowerBound = 1, upperBound = 100;

    // Seed the random number generator
    std::srand(std::time(0));
    number = std::rand() % upperBound + lowerBound; // Random number between 1 and 100

    std::cout << "Welcome to the Number Guessing Game!\n";
    std::cout << "I have chosen a number between " << lowerBound << " and " << upperBound << ".\n";
    std::cout << "Can you guess what it is?\n";

    do {
        std::cout << "Enter your guess: ";
        std::cin >> guess;
        attempts++;

        if (guess > number) {
            std::cout << "Too high! Try again.\n";
        } else if (guess < number) {
            std::cout << "Too low! Try again.\n";
        } else {
            std::cout << "Congratulations! You guessed the number in " << attempts << " attempts.\n";
        }
    } while (guess != number);

    return 0;
}
