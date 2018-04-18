// Discrete_Math_Course
//Assignment 4 


/* 
 * File:   Integer Factorizations
 * Author: Abdallah Felfel
 *ID:  201500505
 * Created on April 17, 2018, 9:38 PM
 */


//STEP#1: get all primes since n/2
//STEP#2: recursion and backtracking on the the tree where every branch has the opportunity to try all the primes since n/2



#include <iostream>
 #include <cmath>
        
using namespace std;


int num = 0;
int k=0;

int *  primes_midway(int, int *);
bool Isprime(int);


  

int  main() {
    int x;
    
    cout << "Enter the integer to be prime factorized:  ";
    cin >>  x;
    cout << "\n";

    
    
    
    
    if (Isprime(x))
    {
    cout << "The prime factors are:  ";
    cout << x;
    
   cout << "\nYou entered a prime number. ";
    
        
    }
    
    else{
    
int * arr = new  int [x/2];
int * factors = new  int [x/2];


    

primes_midway( x, arr ) ;
   

   
     for (int i=0; i <= num ;i++)
     {
      
            while ( (x % arr[i]) == 0  &&  arr[i] !=0  && x != 1 ) 
                { 
                   factors[k] = arr[i];
                     x = x/arr[i];
                     k++;
                }      
   
     }
        
         
              
    cout << "The prime factors are:  ";
       
   for (int i =0; i< k   ;i++)
   {  
       cout << factors[i];
       cout <<" ";
       
       
   }
       cout <<" \n\n";


          
   
   delete [] arr;
   delete [] factors;
   
}
return 0;
 
}



bool Isprime(int x){
    
    bool flag = true;
    
            for (int j=2; j<=sqrt(x) ;j++)
            {
                    if ( x%j ==0 ){
                        flag = false;
                        break;

                    }
            }
            return flag;
        
    
}




int * primes_midway(int x , int *temp )
{
    bool flag;

    for (int i=2 ; i<=x/2 ; i++ )
    {
        flag = false;
            for (int j=2; j<=sqrt(i) ;j++)
            {
                    if ( i%j ==0 ){
                        flag = true;
                        break;

                    }
            }
        
            if (flag ==  false)
            { 
                temp[num] = i;
                num++;

            }
        
    
    }
    
    return temp;
    
}
