#include <iostream>
#include <cstdlib>
#include <ctime>

int main() {
    srand(time(0)); // Initialize random number generator

    char playAgain;
    do {
        // Generate computer's choice
        int BOT_choice = rand() % 3 + 1;

        // Get user input
        int user_choice;
        std::cout << "Enter your choice: \n1. Rock \n2. Paper \n3. Scissors\n";
        std::cin >> user_choice;

        // Display choices
        std::string choices[3] = {"Rock", "Paper", "Scissors"};
        std::cout << "You chose " << choices[user_choice - 1] << "\n";
        std::cout << "BOT chose " << choices[BOT_choice - 1] << "\n";

        // Determine the winner
        if (user_choice == BOT_choice) {
            std::cout << "It's a tie!\n";
        } else if ((user_choice == 1 && BOT_choice == 3) || 
                   (user_choice == 2 && BOT_choice == 1) || 
                   (user_choice == 3 && BOT_choice == 2)) {
            std::cout << "You win!\n";
        } else {
            std::cout << "You lose!\n";
        }

        // Ask if user wants to play again
        std::cout << "Do you want to play again? (y/n): ";
        std::cin >> playAgain;

    } while(playAgain == 'y' || playAgain == 'Y');

    return 0;
}
