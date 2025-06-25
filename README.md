# numberguessinggame
c++ code

#include <iostream>
#include <cstdlib>
#include <ctime>

int main() {
    // Seed the random number generator
    srand(time(0));

    // Generate a random number between 1 and 100
    int numberToGuess = rand() % 100 + 1;

    int attempts = 0;
    int userGuess;

    std::cout << "Welcome to the number guessing game!" << std::endl;
    std::cout << "I'm thinking of a number between 1 and 100." << std::endl;

    while (true) {
        // Ask the user for their guess
        std::cout << "Take a guess: ";
        std::cin >> userGuess;

        // Check if the input is valid
        if (std::cin.fail()) {
            std::cout << "That's not a valid number!" << std::endl;
            std::cin.clear();
            std::cin.ignore(10000, '\n');
            continue;
        }

        // Increment the number of attempts
        attempts++;

        // Check if the user's guess is correct
        if (userGuess == numberToGuess) {
            std::cout << "Congratulations! You guessed the number in " << attempts << " attempts." << std::endl;
            break;
        } else if (userGuess < numberToGuess) {
            std::cout << "Your guess is too low. Try again!" << std::endl;
        } else {
            std::cout << "Your guess is too high. Try again!" << std::endl;
        }
    }

    return 0;
}
