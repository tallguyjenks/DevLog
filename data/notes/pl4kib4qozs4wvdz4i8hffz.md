

### Example

```cpp
#include <iostream>
using namespace std;

class GameInfo {
   public:
      void SetPlayer1PlayA(int playScore); // Mutator
      void SetPlayer1PlayB(int playScore); // Mutator
      void SetPlayer2PlayA(int playScore); // Mutator
      void SetPlayer2PlayB(int playScore); // Mutator

      int  GetPlayer1PlayA() const;        // Accessor
      int  GetPlayer1PlayB() const;        // Accessor
      int  GetPlayer2PlayA() const;        // Accessor
      int  GetPlayer2PlayB() const;        // Accessor

      int  GetPlayer1HighScore() const;    // Accessor
      int  GetPlayer2HighScore() const;    // Accessor

   private:
      int player1PlayA;
      int player1PlayB;
      int player2PlayA;
      int player2PlayB;
      int MaxOfPair(int num1, int num2) const; // Private helper fct
};

void GameInfo::SetPlayer1PlayA(int playScore) {
   player1PlayA = playScore;
}

void GameInfo::SetPlayer1PlayB(int playScore) {
   player1PlayB = playScore;
}

void GameInfo::SetPlayer2PlayA(int playScore) {
   player2PlayA = playScore;
}

void GameInfo::SetPlayer2PlayB(int playScore) {
   player2PlayB = playScore;
}

int  GameInfo::GetPlayer1PlayA() const {
   return player1PlayA;
}

int  GameInfo::GetPlayer1PlayB() const {
   return player1PlayB;
}

int  GameInfo::GetPlayer2PlayA() const {
   return player2PlayA;
}

int  GameInfo::GetPlayer2PlayB() const {
   return player2PlayB;
}

int GameInfo::GetPlayer1HighScore() const {
   return MaxOfPair(player1PlayA, player1PlayB);
}

int GameInfo::GetPlayer2HighScore() const {
   return MaxOfPair(player2PlayA, player2PlayB);
}

int GameInfo::MaxOfPair(int num1, int num2) const {
   if (num1 > num2) {
      return num1;
   }
   else {
      return num2;
   }
}

int main() {
   GameInfo funGame;

   funGame.SetPlayer1PlayA(88);
   funGame.SetPlayer1PlayB(97);
   funGame.SetPlayer2PlayA(74);
   funGame.SetPlayer2PlayB(40);

   cout << "Player1 playA: " << funGame.GetPlayer1PlayA() << endl;

   cout << "Player1 max: " << funGame.GetPlayer1HighScore() << endl;
   cout << "Player2 max: " << funGame.GetPlayer2HighScore() << endl;

   return 0;
}
```
