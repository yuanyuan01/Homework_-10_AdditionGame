# Homework_-10_AdditionGame
```
We are going to do the addition game using for loops, custom method calls, and an array.
```

## Code
~~~
import java.util.Scanner;

public class LoopsAndMethodsAdditonGame {
	public static void main(String[] args) {
		//System.out.println("Hello class.");
		
		//Call the addition game method.
		AdditonGameMethod();
	}
	public static void AdditonGameMethod() {
		//System.out.println("Inside the addition game method.");
		
		int[] gameVariables = new int[4];
		gameVariables[0] = 5; //hardness;
		//int hardness = gameVariables[0];
		gameVariables[1] = 2; //hardnessStep;
		//int hardnessStep = 2;
		gameVariables[2] = 0; //score;
		//int score = 0;
		gameVariables[3] = 0; // 1 for true, 0 for false
		
		// Set up my for loop to go through the number of rounds
		int numberOfRounds = 3;
		for(int roundNumber = 1; 
		roundNumber <= numberOfRounds;  
		roundNumber = roundNumber + 1){
			//System.out.println("Inside the for loop. Round: " + roundNumber);
			System.out.print("Round " + roundNumber + " of " + numberOfRounds + ". ");
			gameVariables = getAndCheckStudentAnswer(gameVariables);
			if(gameVariables[3] == 1){
				System.out.print("Your score was " + gameVariables[2] + " and is now ");
				gameVariables[2] = gameVariables[2] + gameVariables[0];
				System.out.print(gameVariables[2] + ". ");
				
				if(roundNumber<numberOfRounds){
					System.out.print("Your hardness was " + gameVariables[0] + " and is now ");
					gameVariables[0] = gameVariables[0] * gameVariables[1];
					System.out.println(gameVariables[0] + ".");
				}
			}else{
				System.out.print("Your score is " + gameVariables[2] + ". ");
				if(roundNumber<numberOfRounds){
					System.out.print("Your hardness was " + gameVariables[0] + " and is now ");
					if(gameVariables[0]>5){
						gameVariables[0] = gameVariables[0] / gameVariables[1];
					}
					System.out.println(gameVariables[0] + ".");
					
				}
				
			}
		}
		System.out.print("\nThe game is complete. ");
		System.out.println("Your final score was " + gameVariables[2] );
	}
	
	public static int[] getAndCheckStudentAnswer(int[] gameVariables) {
		//System.out.println("Inside get and check student answer method.");
		int number1 = (int)(Math.random()*gameVariables[0]);
		int number2 = (int)(Math.random()*gameVariables[0]);
		System.out.print("Add " + number1 + " and " + number2 +": ");
		//Scanner input = new Scanner(System.in);
		//int studentAnswer = input.nextInt();
		Scanner get = new Scanner(System.in);
		int studentAnswer = get.nextInt();
		if(studentAnswer == (number1 + number2)){
			System.out.print("Correct. ");
			gameVariables[3] = 1;
			
		}else{
			System.out.println("Nice try, but the correct answer was " 
					+ (number1 + number2) + ".");
			gameVariables[3] = 0;
		}
		return gameVariables;
	}
~~~
