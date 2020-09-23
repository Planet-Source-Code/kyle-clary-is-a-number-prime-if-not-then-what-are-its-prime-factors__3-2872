<div align="center">

## Is a number prime? if not then what are its prime factors?


</div>

### Description

Enter a number and the program will determine if it is prime. If the number is not prime the program will find the prime factors. For really big numbers it should only take a few seconds to process other than that it's lightning fast
 
### More Info
 
input a positive integer if the number is not an int then the program errors

you might want to know how to determine prime factors on paper

returns prime factors

only enter whole numbers!


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Kyle Clary](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/kyle-clary.md)
**Level**          |Beginner
**User Rating**    |3.7 (11 globes from 3 users)
**Compatibility**  |C\+\+ \(general\)
**Category**       |[Math](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/math__3-12.md)
**World**          |[C / C\+\+](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/c-c.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/kyle-clary-is-a-number-prime-if-not-then-what-are-its-prime-factors__3-2872/archive/master.zip)

### API Declarations

iostream.h


### Source Code

```
//////////////////////////////////////////////////////////////////////
//A BrainChild of Kyle Clary
//Program does a prime factorization for a number
//////////////////////////////////////////////////////////////////////
#include<iostream.h>
//Function Declerations
int GetInt();
void Factor(int num,bool prime);
bool CheckPrime(int num);
//main
int main()
{
	bool prime;
	int num;
	char quit;
	do							//Run program as many times as user
	{							//would like to
		num = GetInt();
		prime = CheckPrime(num);
		Factor(num,prime);
		cout<< endl <<"Would you like to try again? Y or N ";
		cin>>quit;
		cout<< endl;
	}while(quit=='Y' || quit=='y');
	return 0;
}
//////////////////////////////////////////////////////////////////////
//Function gets number to factorize
//input: none
//output: num
//////////////////////////////////////////////////////////////////////
int GetInt()
{
	int num;
	do									//make sure number is positive
	{
		cout<<"Enter a positive integer: ";
		cin>>num;
	}while(num<=0);
	return num;
}
//////////////////////////////////////////////////////////////////////
//Function checks if number is prime
//input: num
//output: bool
//////////////////////////////////////////////////////////////////////
bool CheckPrime(int num)
{
	bool prime = true;
	for(int r=2;r<=(num-1);r++)	//mod user's number from 2 till
	{							//user's number-1 because all numbers
								//have factors of 1 and itself so you
		if(num%r==0)			//only need to check from 2 to the number-1
			prime = false;			//if number mod any number from 2 to
	}								//number-1 is 0 then number is not prime
	return prime;
}
//////////////////////////////////////////////////////////////////////
//Function determines prime factors of number given by user
//input: num
//output: none
//////////////////////////////////////////////////////////////////////
void Factor(int num,bool prime)
{
	if(prime==true)			//if number is prime print special prime
	{						//number message
		cout<< endl << num << " is prime. Factors are " << num
			<< " and 1" << endl;
	}
	else			//if number is not prime then find prime factors
	{
		cout<< endl << endl << "The Prime factors of " << num <<" are:"
			<< endl << endl;
		for(int i=2;i<=num;i++)	//for loop controls what number to mod user
		{						//number by to determine if it is a factor
			while(num%i==0)	//while loop tests if user number is a factor
			{				//if number is a factor and prime it prints the prime
				num = num/i;	//factor and terminates the loop if the factor is
				cout<< i << endl;//not prime then it finds the prime factors of
			}					 //the factor and prints them
		}
	}
}
```

