# Files-in-C
Using fwrite() and fread()

Filename can be any of your file.

Writing contents into a file using fwrite()
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
            fp=fopen(FILE_NAME,"a");
            printf("Enter the account_number: ");
            scanf("%d",&c1.account_number);
            printf("Enter the name of customer: ");
            scanf("%s",c1.name);
            printf("Enter the balance_amount: ");
            scanf("%d",&c1.balance_amount);
            fwrite(&c1,sizeof(struct Customer),1,fp);
            fclose(fp);
      }
