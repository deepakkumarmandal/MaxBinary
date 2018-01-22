/*Program to convert Decimal into Binary and then print maximum number of consecutive 1's*/

import java.io.*;
import java.util.*;

public class Solution {
   

    public static void main(String[] args) {
        /* Enter your code here. Read input from STDIN. Print output to STDOUT. Your class should be named Solution. */
        Scanner s=new Scanner(System.in);
        int num=s.nextInt();
        int tos=0;
        int size=10;
        int count=0;
        String stack[]=new String[size];
        int c=0;
        while(num>0)
        {
         int rem=num%2;
         num=num/2;
        if(tos<size-1)
        {
          if(rem==1)
          {  
          stack[tos]="1";
          tos++;
          }
          else
          {
            stack[tos]="0";
              tos++;
          }
        }
        else
        { 
          if(rem==1)
          {  
          stack[tos]="1";
          tos++;
          }
          else
          {
            stack[tos]="0";
              tos++;
          }
          
          String newstack[]=new String[size*2];
          for(int i=0;i<size;i++)
          {
              newstack[i]=stack[i];
          }
           stack=newstack;
           size=size*2;
         }
        }
        tos--;
        while(tos>=1)
        {  
            while(stack[tos]=="1")
            {
               ++count;
                tos--;
               if(tos<0)
                   break;
                  
            }
            if(c<count)
            {
                c=count;
            }
            count=0; 
         tos--;
        }
        System.out.println(c);
        
      }
}