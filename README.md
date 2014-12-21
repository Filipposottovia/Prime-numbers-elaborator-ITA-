Prime-numbers-elaborator-ITA-
=============================

//This program (in Italian) will tell the user whether a certain number is prime or not and will also display all the prime numbers in a chosen interval. Written in C++

#include <iostream>


int main(int argc, const char * argv[]) {
    int flag=0;
    std::cout<<"      ==============================================="<<std::endl;
    std::cout<<"      | BENVENUTO NELL'ELABORATORE DI NUMERI PRIMI! |"<<std::endl;
    std::cout<<"      ==============================================="<<std::endl;
    do
    {
        std::cout<<std::endl<<"Per controllare se un certo numero è primo premere 1, per ottenere l'elenco dei numeri primi in un dato intervallo premere 2"<<std::endl;
        int scelta;
        std::cin>>scelta;
        if (scelta==1)
        {
            int number, count=0;
            std::cout<<"Scrivere un numero per vedere se è primo o no"<<std::endl;
            std::cin>>number;
            for (int a=1; a<=number; a++)
            {
                if (number%a==0) count++;
            }
            if (count==2) std::cout<<number<<" è un numero primo"<<std::endl;
            else std::cout<<number<<" non è un numero primo"<<std::endl;
        }
        else if (scelta==2)
        {
            int firstnumber;
            int lastnumber;
            int counttot=0;
            std::cout<<std::endl<<"Scrivere due numeri interi (premere INVIO dopo avere digitato ciascun numero), appariranno tutti i numeri primi nell'intervallo fra di essi"<<std::endl;
            std::cin>>firstnumber;
            std::cin>>lastnumber;
            
            if (firstnumber==2 && lastnumber==2)std::cout<<" "<<2<<" ";
            else if (firstnumber<=2 && lastnumber==3)
            {
                std::cout<<2<<" ";
                std::cout<<" "<<3;
            }
            else if (firstnumber==3 && lastnumber==3)  std::cout<<"3";
            
            else if (firstnumber<=2 && lastnumber>=5)
            {
                std::cout<<2<<" ";
                std::cout<<" "<<3<<" ";
                std::cout<<" "<<5<<" ";
            }
            else if (firstnumber==3 && lastnumber==5)
            {
                
                std::cout<<3<<" ";
                std::cout<<" "<<5<<" ";
            }
            for (int i=firstnumber; i<=lastnumber; i++)
                for (int j=2; j<i/2; j++)
                {
                    if (i<=6) break;
                    if (i%j==0) break;
                    if (i/2<=j+1)
                    {
                        std::cout<<" "<<i<<" ";
                        counttot++;
                    }
                }
            if ((firstnumber==3 && lastnumber==3) or (firstnumber==2 && lastnumber==2)) std::cout<<std::endl<<"Nell'intervallo c'è 1 numero primo"<<std::endl;
            else if ((firstnumber<=2 && lastnumber==3)) std::cout<<std::endl<<std::endl<<"Nell'intervallo ci sono 2 numeri primi"<<std::endl;
            else if (firstnumber<=2 && lastnumber<7) std::cout<<std::endl<<std::endl<<"Nell'intervallo ci sono 3 numeri primi"<<std::endl;
            else if (firstnumber==3 && lastnumber==5)std::cout<<std::endl<<std::endl<<"Nell'intervallo ci sono 3 numeri primi"<<std::endl;
            else if (firstnumber<=2 && lastnumber>=7)
            {
                int contatore=counttot+3;
                float interv=lastnumber-firstnumber+1;
                float fraz=contatore/interv;
                float percent=fraz*100;
                std::cout<<std::endl<<std::endl<<"Nell'intervallo ci sono "<<contatore<<" numeri primi  ("<<percent<<"% del totale)"<<std::endl;
            }
            else if (firstnumber==3 && lastnumber>=7)
            {
                int contatore=counttot+2;
                float interv=lastnumber-firstnumber+1;
                float fraz=contatore/interv;
                float percent=fraz*100;
                std::cout<<std::endl<<std::endl<<"Nell'intervallo ci sono "<<contatore<<" numeri primi ("<<percent<<"% del totale)"<<std::endl;
            }
            else if (firstnumber==5 && lastnumber>=7)
            {
                int contatore=counttot+1;
                float interv=lastnumber-firstnumber+1;
                float fraz=contatore/interv;
                float percent=fraz*100;
                std::cout<<std::endl<<std::endl<<"Nell'intervallo ci sono "<<contatore<<" numeri primi ("<<percent<<"% del totale)"<<std::endl;
            }
            else if (firstnumber>=7 && lastnumber>=7)
            {
                float interv=lastnumber-firstnumber+1;
                float fraz=counttot/interv;
                float percent=fraz*100;
                std::cout<<std::endl<<std::endl<<"Nell'intervallo ci sono "<<counttot<<" numeri primi ("<<percent<<"% del totale)"<<std::endl;
            }
        }
        std::cout<<std::endl<<"Per ripartire digitare 0, altrimenti qualsiasi altra cifra"<<std::endl;
        std::cin>>flag;
    }
    while (flag==0);
    std::cout<<"Copyright Filippo Sottovia 2014";
    return 0;
}
