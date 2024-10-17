# Dep-task5
#include <iostream>
#include <string>

using namespace std;

void showIntroduction() {
    cout << "Welcome to the Adventure Game!" << endl;
    cout << "You find yourself in a dark forest." << endl;
    cout << "Your goal is to find the treasure hidden in the castle." << endl;
}

void forestScene() {
    cout << "\nYou are in the forest. You can go left to the river or right to the cave." << endl;
    cout << "1. Go to the river\n2. Go to the cave\nChoose an option (1 or 2): ";
}

void riverScene() {
    cout << "\nAt the river, you see a boat. Do you want to:\n";
    cout << "1. Take the boat\n2. Swim across\nChoose an option (1 or 2): ";
}

void caveScene() {
    cout << "\nIn the cave, you encounter a dragon. Do you want to:\n";
    cout << "1. Fight the dragon\n2. Run away\nChoose an option (1 or 2): ";
}

void gameLoop() {
    int choice;
    bool inForest = true;

    while (inForest) {
        forestScene();
        cin >> choice;

        switch (choice) {
            case 1:
                riverScene();
                cin >> choice;
                if (choice == 1) {
                    cout << "You safely crossed the river and found the treasure! You win!" << endl;
                    inForest = false;
                } else {
                    cout << "You swam across but got swept away by the current. Game Over!" << endl;
                    inForest = false;
                }
                break;

            case 2:
                caveScene();
                cin >> choice;
                if (choice == 1) {
                    cout << "You bravely fought the dragon but lost. Game Over!" << endl;
                    inForest = false;
                } else {
                    cout << "You ran away and safely returned to the forest." << endl;
                }
                break;

            default:
                cout << "Invalid choice. Please choose 1 or 2." << endl;
                break;
        }
    }
}

int main() {
    showIntroduction();
    gameLoop();
    return 0;
}
