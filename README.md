# java1
#Java Case Switch and Method

import java.util.*;

public class Main 
{
	public static void main(String[] args) 
	{
		Scanner input = new Scanner(System.in);
		//Variables
		String str;
		int choice = 0;
		//User input
		System.out.println("Enter a string: ");
		str = input.nextLine();
		//Make sure they enter something
		while(str.length() <= 0)
		{
			System.out.println("You must enter at least one character.\nTry again.");
			str = input.nextLine();
		}
		menu();
		choice = input.nextInt();
		while (choice != -1)
		{
			if (choice > 0 && choice < 5)
			{
				switch(choice)
				{
				case 1:
					numberOfWords(str);
					break;
				case 2:
					allCapitals(str);
					break;
				case 3:
					allLowers(str);
					break;
				case 4:
					reverseOrder(str);
					break;
				}//end switch
			}//end if
			else
				System.out.println("Incorrect entry, try again.");
			menu();
			choice = input.nextInt();
		}//end while		
	}//end main
		
	public static void menu()
	{
		System.out.println("Enter 1 to display the number of words in the string: ");
		System.out.println("Enter 2 to display the string in all capital letters: ");
		System.out.println("Enter 3 to display the string in all lower case letters: ");
		System.out.println("Enter 4 to display the string in reverse order: ");
		System.out.println("Enter -1 to exit: ");
	}
	
	public static void reverseOrder(String str)
	{
		for(int i = str.length() - 1; i >=0; i--)
		{
			System.out.print(str.charAt(i));
		}
		System.out.println();
	}
  
	public static void allCapitals(String str)
	{
		String upperCase;
		upperCase = str.toUpperCase();
		System.out.println("Your string in upper case:\n" + upperCase);		
	}
  
	public static void allLowers(String str)
	{
		String lowerCase;
		lowerCase = str.toLowerCase();
		System.out.println("Your string in lower case:\n" + lowerCase);
	}
  
	public static void numberOfWords(String str)
	{
		//method variables
		int tokens;		
		StringTokenizer strToken = new StringTokenizer(str);
		tokens = strToken.countTokens();
		System.out.println("There are " + tokens + " words in that string.");	
	}
}
