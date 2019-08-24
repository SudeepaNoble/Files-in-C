# Files-in-C
Using fread()
Using fread() to read the details from a file

************Program************
    #include<stdio.h>
    #include<string.h>
    #define LENGTH 50
    #define FILE_NAME "CustomerDetails.dat"
    struct Customer
    {
      int account_number;
      char name[LENGTH];
      int balance_amount;
     };
    void main()
    {
      struct Customer c1;
      FILE *fp;
      fp=fopen(FILE_NAME,"r");
      printf("Account details are: ");
      while((fread(&c1,sizeof(struct Customer),1,fp))==1)
      {
        printf("\nAccount_Number: %d,Name: %s,Balance_Amount: %d",c1.account_number,c1.name,c1.balance_amount);
      }
      fclose(fp);
    }
