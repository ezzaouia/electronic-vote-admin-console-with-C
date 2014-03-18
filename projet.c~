#include <stdio.h>
#include<stdlib.h>
#include<conio.h>
#include<windows.h>
#include<time.h>
#include<string.h>
#include <limits.h>
#include <malloc.h>
#define TAILLE_MAX 10000

/**
* Spring 2010
* @author Oussama Fatri
* @author Mohamed Ezzaouia
*
*/

int n;

typedef struct personne
            {
              char nom[30];
              char age[30] ;
              int nbredvote;
                            }votant;
                            
 votant rep1[1000],rep2[1000],rep3[1000],rep4[1000];
//administrateur
void Taper_Mot_Passe(void)
    {
        int i,t;
        char a,y;
        char Password[7];
        char Etoile[7];
        printf("\t\t\tTAPER LE PASSWORD SVP : \t");
        printf("\a\a");
        i = 0;
        t = 0;
        while (t!=13)
            {
                a = getch();
                t = a;
                if (t!=13)
                    {
                        if (t==8)
                            {
                                system("cls");
                                i = i-1;
                                Etoile[i] = '\0';
                                printf("\t\t\tTAPER LE PASSWORD SVP : \t");
                                printf("%s",Etoile);
                            }
                        else
                            {
                                printf("*");
                                Password[i] = a;
                                Etoile[i] = '*';
                                i = i+1;
                            }
                    }
                else Password[i]='\0';
            }
        if (strcmp(Password,"user")!=0)
            {
                printf("\a");
                gotoxy(17,30);
                printf("!! VOTRE MOT DE PASSE SVP N\'EST PAS VALIDE.!\n\n\n");
                gotoxy(17,32);
                printf("ok taper une touche pr continuer");
                getch();
                scanf("%c",&y);
                system("cls");
                menu1();
            }
        else
            {
                system("cls");
               // menu_admin();
                printf("\n");


            }

    }


void ajouter_adherent(void)
{
               FILE* fichier = NULL;
               int i;
           /* char adhesion[30] ,*/ char nom[30],prenom[30],adresse[30],email[30],ville[30],age[30],institution_de_tutelle[30],fct_ds_institution[30];

    fichier = fopen("adherents.txt", "a");

    if (fichier != NULL)
    {

         printf("nmber d'adherents a ajouter");
         int nmber;scanf("%d",&nmber);

       for(i=1;i<=nmber;i++)
              {
                      int adhesion;
                      srand (time (NULL));
                      adhesion= Random (1,555);

                     printf("\nvotre adhesion est %d ",adhesion);
                     printf("\n\n\n");

                     printf("\t+-----------------------------------------+|\n");
                     printf("\t|NOM                    ||");scanf("%s. ",&nom);
                     printf("\t+-----------------------------------------+|\n");
                     printf("\t|PRENOM                 ||");scanf("%s. ",&prenom);
                     printf("\t+-----------------------------------------+|\n");
                     printf("\t|ADRESSE                ||");scanf("%s. ",&adresse);
                     printf("\t+-----------------------------------------+|\n");
                     printf("\t|EMAIL                  ||");scanf("%s. ",&email);
                     printf("\t+-----------------------------------------+|\n");
                     printf("\t|VILLE                  ||");scanf("%s. ",&ville);
                     printf("\t+-----------------------------------------+|\n");
                     printf("\t|AGE                    ||");scanf("%s. ",&age);
                     printf("\t+-----------------------------------------+|\n");
                     printf("\t|INSTITUTION DE TUTELLE ||");scanf("%s. ",&institution_de_tutelle);
                     printf("\t+-----------------------------------------+|\n");
                     printf("\t|FCT DS INSTITUTION     ||");scanf("%s. ",&fct_ds_institution);
                     printf("\t+-----------------------------------------+|\n");

            fprintf(fichier,"%d %s %s %s %s %s %s %s %s\n", adhesion,nom,prenom,adresse,email,ville,age,institution_de_tutelle,fct_ds_institution);

              }



          fclose(fichier); // On ferme le fichier qui a ้t้ ouvert
    }
    else
    {
        // On affiche un message d'erreur si on veut
        printf("Impossible d'ouvrir le fichier adherents.txt");
    }
}

//affichage des adherents

void afficher_adherents()
       {
    FILE* fichier = NULL;
    int caractereActuel = 0;

    fichier = fopen("adherents.txt", "r");

    if (fichier != NULL)
    {
        caractereActuel = fgetc(fichier); // On initialise caractereActuel

	// Boucle de lecture des caract่res un เ un
	while (caractereActuel != EOF) // On continue tant que fgetc n'a pas retourn้ EOF (fin de fichier)
	{


	    printf("%c", caractereActuel); // On affiche le caract่re stock้ dans caractereActuel
  	    caractereActuel = fgetc(fichier); // On lit le caract่re suivant
	}

	fclose(fichier);
    }


       else
    {
        // On affiche un message d'erreur si on veut
        printf("Impossible d'ouvrir le fichier adherents.txt");
    }

}


 //calculer le nbre des adherents

int afficher_nbre_adherents()
       {
    FILE* fichier = NULL;
    int caractereActuel = 0,i=0;

    fichier = fopen("adherents.txt", "r");

    if (fichier != NULL)
    {
        caractereActuel = fgetc(fichier); // On initialise caractereActuel

	// Boucle de lecture des caract่res un เ un
	while (caractereActuel != EOF) // On continue tant que fgetc n'a pas retourn้ EOF (fin de fichier)
	{
          if ( caractereActuel=='\n')
              i++;

	   // printf("%c", caractereActuel); // On affiche le caract่re stock้ dans caractereActuel
  	    caractereActuel = fgetc(fichier); // On lit le caract่re suivant
	}

	fclose(fichier);
    }


       else
    {
        // On affiche un message d'erreur si on veut
        printf("Impossible d'ouvrir le fichier adherents.txt");
    }
             return i;
}


//chercher l'existence d'un adherent par code d'adhesion

void test_exitence()
       {
            int code[1]={0};
       int buffer_code[1]={0};

       FILE* fichier = NULL;

       fichier=fopen("adherents.txt","r");
 if (fichier != NULL)
      {

       printf("DONNER VOTRE CODE  :");
       scanf("%d",&code[0]);


       while(fscanf(fichier,"%d",&buffer_code[0])!=NULL)
       {
              if(buffer_code[0]==code[0])
              {
                     gotoxy(18,33);
                     printf("LE CODE SAISIE EST TROUVE \n");
                     break;
              }
             // else printf("NON");

       while(fgetc(fichier)!='\n');
       }
}

 else
    {
        // On affiche un message d'erreur si on veut
        printf("Impossible d'ouvrir le fichier adherents.txt");
    }
}


//test d'existence pour s'inscrire aux elections
void test_exitence_par_code()
       {
            int code[1]={0};
       int buffer_code[1]={0};

       FILE* fichier = NULL;

       fichier=fopen("adherents.txt","r");
 if (fichier != NULL)
      {

       printf("DONNER VOTRE CODE  :");
       scanf("%d",&code[0]);


       while(fscanf(fichier,"%d",&buffer_code[0])!=NULL)
       {
              if(buffer_code[0]==code[0])
              {
                     printf("LE CODE SAISIE EST TROUVE \n");
                     //enregistrement d'inscription
                    voter();
                     break;
              }

          else    printf("\n ! IL N\'EXISTE PAS\n\n\n");
              break;
       while(fgetc(fichier)!='\n');
       }

}

 else
    {
        // On affiche un message d'erreur si on veut
        printf("Impossible d'ouvrir le fichier adherents.txt");
    }
}


void enregistrer1(votant * rep)
{
       FILE* fichier = NULL;
       int i = 0,n;
       fichier=fopen("president.txt","w+");
       if(fichier==NULL)
       {
              printf("Erreur lors de la lecture du fichier\n");
       }
       else
       {
              printf("Entrez le nombre :");
              scanf("%d",&n);
              getchar();
              for (i=0;i<n;i++)
              {
                     printf("le nom");
                     gets(rep[i].nom);
                     printf("le age");
                     gets(rep[i].age);
                     rep[i].nbredvote=0;
              }
              fwrite(&n,sizeof(int),1,fichier);
              fwrite(rep,sizeof(votant),n,fichier);
       }
       fclose(fichier);
}


void enregistrer2(votant * rep)
{
       FILE* fichier = NULL;
       int i = 0,n;
       fichier=fopen("vice_president.txt","w+");
       if(fichier==NULL)
       {
              printf("Erreur lors de la lecture du fichier\n");
       }
       else
       {
              printf("Entrez le nombre :");
              scanf("%d",&n);
              getchar();
              for (i=0;i<n;i++)
              {
                     printf("le nom");
                     gets(rep[i].nom);
                     printf("le age");
                     gets(rep[i].age);
                     rep[i].nbredvote=0;
              }
              fwrite(&n,sizeof(int),1,fichier);
              fwrite(rep,sizeof(votant),n,fichier);
       }
       fclose(fichier);
}


void enregistrer3(votant * rep)
{
       FILE* fichier = NULL;
       int i = 0,n;
       fichier=fopen("membre_ce.txt","w+");
       if(fichier==NULL)
       {
              printf("Erreur lors de la lecture du fichier\n");
       }
       else
       {
              printf("Entrez le nombre :");
              scanf("%d",&n);
              getchar();
              for (i=0;i<n;i++)
              {
                     printf("le nom");
                     gets(rep[i].nom);
                     printf("le age");
                     gets(rep[i].age);
                     rep[i].nbredvote=0;
              }
              fwrite(&n,sizeof(int),1,fichier);
              fwrite(rep,sizeof(votant),n,fichier);
       }
       fclose(fichier);
}

void enregistrer4(votant * rep)
{
       FILE* fichier = NULL;
       int i = 0,n;
       fichier=fopen("aucune.txt","w+");
       if(fichier==NULL)
       {
              printf("Erreur lors de la lecture du fichier\n");
       }
       else
       {
              printf("Entrez le nombre :");
              scanf("%d",&n);
              getchar();
              for (i=0;i<n;i++)
              {
                     printf("le nom");
                     gets(rep[i].nom);
                     printf("le age");
                     gets(rep[i].age);
                     rep[i].nbredvote=0;
              }
              fwrite(&n,sizeof(int),1,fichier);
              fwrite(rep,sizeof(votant),n,fichier);
       }
       fclose(fichier);
}






//sinscrire aux election

void sinscrir_o_elections()
       {


             // votant rep1[1000],rep2[1000],rep3[1000],rep4[1000];
             // rep=(votant *)malloc(sizeof(votant));
              char cod;
              printf("\n0- president \n");
              printf("1- vice-persident\n");
              printf("2- ce\n");
              printf("3- aucune\n");
              printf("4- fin\n");
              printf("?\n");

             cod=getchar();

              switch(cod)
                     {
                            case '0' :
                            {
                                          enregistrer1(rep1);
                            }break;

                            case '1' :
                            {
                                          enregistrer2(rep2);
                            }break;

                            case '2' :
                            {
                                            enregistrer3(rep3);
                            }break;

                            case '3' :
                            {
                                            enregistrer4(rep4);
                            }break;

                            case '4' :
                            {
                                   system("cls");
                                   exit(0);
                            }break;

                            default :
                            {
                               printf("\n\nDesole votre proposition ne figure pas dans la liste des choix.");
                               system("cls");
                               //sinscrir_o_elections();
                            }break;
                     }
       }


void charger1(votant * rep)
{
       FILE* fichier = NULL;
       int person = 0;
       char nom[40]="";
       int i = 0;
       fichier=fopen("president.txt","r");
       if(fichier==NULL)
       {
              printf("Bienvenue, c'est la premiere fois que vous utiliser notre application\n");
       }
       else
       {
              fread(&n,sizeof(int),1,fichier);
              fread(rep,sizeof(votant),n,fichier);
              for (i=0; i<n;i++) printf("%s %s %d\n",rep[i].nom,rep[i].age,rep[i].nbredvote);

              printf("\nVOUS VOTER SUR (le nom) : ?");
              getchar();
              gets(nom);
              for(person=0;person<n;person++)
              {
                     if(strcmp(nom,rep[person].nom)==0)
                     {
                            incremente_nbrvote1(rep,person);
                     }
              }
              for (i=0; i<n;i++) printf("%s %s %d\n",rep[i].nom,rep[i].age,rep[i].nbredvote);
       }
       fclose(fichier);
}

void charger2(votant * rep)
{
       FILE* fichier = NULL;
       int person = 0;
       char nom[40]="";
       int i = 0;
       fichier=fopen("vice_president.txt","r");
       if(fichier==NULL)
       {
              printf("Bienvenue, c'est la premiere fois que vous utiliser notre application\n");
       }
       else
       {
              fread(&n,sizeof(int),1,fichier);
              fread(rep,sizeof(votant),n,fichier);
              for (i=0; i<n;i++) printf("%s %s %d\n",rep[i].nom,rep[i].age,rep[i].nbredvote);
              printf("\nVOUS VOTER SUR (le nom) : ?");
              getchar();
              gets(nom);
              for(person=0;person<n;person++)
              {
                     if(strcmp(nom,rep[person].nom)==0)
                     {
                            incremente_nbrvote2(rep,person);
                     }
              }
              for (i=0; i<n;i++) printf("%s %s %d\n",rep[i].nom,rep[i].age,rep[i].nbredvote);
       }
       fclose(fichier);
}


void charger3(votant * rep)
{
       FILE* fichier = NULL;
       int person = 0;
       char nom[40]="";
       int i = 0;
       fichier=fopen("membre_ce.txt","r");
       if(fichier==NULL)
       {
              printf("Bienvenue, c'est la premiere fois que vous utiliser notre application\n");
       }
       else
       {
              fread(&n,sizeof(int),1,fichier);
              fread(rep,sizeof(votant),n,fichier);
              for (i=0; i<n;i++) printf("%s %s %d\n",rep[i].nom,rep[i].age,rep[i].nbredvote);
              printf("\nVOUS VOTER SUR (le nom) : ?");
              getchar();
              gets(nom);
              for(person=0;person<n;person++)
              {
                     if(strcmp(nom,rep[person].nom)==0)
                     {
                            incremente_nbrvote3(rep,person);
                     }
              }
              for (i=0; i<n;i++) printf("%s %s %d\n",rep[i].nom,rep[i].age,rep[i].nbredvote);
       }
       fclose(fichier);
}

//voter
void voter()
       {
              //tset_dexistence..
              //si oui..
              char cod;
              printf("\n\n\nVous voter pour \n\n");
              printf("\t0- president \n");
              printf("\t1- vice-president \n");
              printf("\t2- un membre de CE \n");
              printf("\t3- fin\n\n");
              printf(" choisir ?");
              cod=getchar();
              //scanf("%c",&cod);

       switch(cod)

              {
                     case '0':
                            {
                                   charger1( rep1 );
                            }break;

                      case '1':
                            {
                                    charger2(rep2);
                            }break;

                      case '2':
                            {
                                    charger3(rep3);
                            }break;

                      case '3':
                            {
                                   exit(0);
                            }break;

                       default :
                            {
                               printf("\n\nDesole votre proposition ne figure pas dans la liste des choix.");
                               system("cls");
                               voter();
                            }break;

              }



       }
//incremente_nbrvote

void incremente_nbrvote1(votant *rep,int person){

       FILE* fichier=NULL;

       fichier=fopen("president.txt","w");


       rep[person].nbredvote++;
       fwrite(&n,sizeof(int),1,fichier);

       fwrite(rep,sizeof(votant),n,fichier);

       fclose(fichier);
}

void incremente_nbrvote2(votant *rep,int person){

       FILE* fichier=NULL;

       fichier=fopen("vice_president.txt","w");


       rep[person].nbredvote++;
       fwrite(&n,sizeof(int),1,fichier);

       fwrite(rep,sizeof(votant),n,fichier);

       fclose(fichier);
}

void incremente_nbrvote3(votant *rep,int person){

       FILE* fichier=NULL;

       fichier=fopen("membre_ce.txt","w");


       rep[person].nbredvote++;
       fwrite(&n,sizeof(int),1,fichier);

       fwrite(rep,sizeof(votant),n,fichier);

       fclose(fichier);
}

void incremente_nbrvote(votant *rep,int person){

       FILE* fichier=NULL;

       fichier=fopen("fichier_president.txt","w");


       rep[person].nbredvote++;
       fwrite(&n,sizeof(int),1,fichier);

       fwrite(rep,sizeof(votant),n,fichier);

       fclose(fichier);
}





void supprimer_adherent()
       {
           FILE *F, *FW;
           char  s[30],nomasupp[30];
           char adhesion[30] ,  nom[30],prenom[30],adresse[30],email[30],ville[30],age[30],institution_de_tutelle[30],fct_ds_institution[30];


       if (NULL == (F = fopen ("adherents.txt", "r")))
              return -1;
       if (NULL == (FW = fopen ("adherents_resultat.txt", "w+")))
              return -1;

                printf ("nom a supprimer ? ");
                scanf ("%s", nomasupp);


       do   {fscanf(F,"%s %s %s %s %s %s %s %s %s\n", adhesion,s,prenom,adresse,email,ville,age,institution_de_tutelle,fct_ds_institution);

       if (strcmp (s, nomasupp) != 0)
              fprintf(FW,"%s %s %s %s %s %s %s %s %s\n", adhesion,s,prenom,adresse,email,ville,age,institution_de_tutelle,fct_ds_institution);
         }
       while (!feof(F));
                fclose (F);
                fclose (FW);

       remove("adherents.txt");
       rename("adherents_resultat.txt", "adherents.txt");
}


//Random
int Random (int _iMin, int _iMax)
       {
                     return (_iMin + (rand () % (_iMax-_iMin+1)));
       }


void intro1()

       {
              cadre();
              gotoxy(15,12);
              printf("\a -- P R O J E T  D E  P R O G R A M M A T I O N  C --");
              Sleep(300);
              gotoxy(15,14);
              printf("\a    -- G E S T I O N  D E S  E L E C T I O N S --    ");
              Sleep(300);
              gotoxy(15,16);
              printf("\a               2 0 1 0 & 2 0 1 1                     ");
              Sleep(300);
              gotoxy(15,18);
              printf("\a                  E N S I A S                        ");
              Sleep(300);
              gotoxy(12,23);
              printf("\aENCADRANTE : Mme EL ASRI .                          ");
              Sleep(300);
              gotoxy(17,26);
              printf("\aREALISER PAR :                         FATRI&EZZAOUIA");



printf("\n\n\n\n\n\n\n\n");

       }

void intro2()
       {
                     cadre();
                     gotoxy(8,16);
                     printf(" บ                    L O A D I N G . .                          บ \n");

       printf("\a");Sleep(800);printf("\a");Sleep(800);printf("\a");Sleep(800);printf("\a");Sleep(800);
       Sleep(200);
       gotoxy(30,16);
       printf("B\a");
       Sleep(200);
       gotoxy(32,16);
       printf("I\a");
       Sleep(200);
       gotoxy(34,16);
       printf("E\a");
       Sleep(200);
       gotoxy(36,16);
       printf("V\a");
       Sleep(200);
       gotoxy(38,16);
       printf("E\a");
       Sleep(500);
       gotoxy(40,16);
       printf("N\a");
       Sleep(200);
       gotoxy(42,16);
       printf("U\a");
       Sleep(200);
       gotoxy(44,16);
       printf("E\a");
       Sleep(200);


       gotoxy(29,18);
       printf("A\a");
       Sleep(200);
       gotoxy(31,18);
       printf("S\a");
       Sleep(200);
       gotoxy(33,18);
       printf("S\a");
       Sleep(200);
       gotoxy(35,18);
       printf("O\a");
       Sleep(200);
       gotoxy(37,18);
       printf("C\a");
       Sleep(200);
       gotoxy(39,18);
       printf("I\a");
       Sleep(200);
       gotoxy(41,18);
       printf("A\a");
       Sleep(200);
       gotoxy(43,18);
       printf("T\a");
       Sleep(200);
       gotoxy(45,18);
       printf("I\a");
       Sleep(200);
       gotoxy(47,18);
       printf("O\a");
       Sleep(200);
       gotoxy(49,18);
       printf("N\a");

       Sleep(200);
       gotoxy(30,20);
       printf("O\a");
       Sleep(200);
       gotoxy(32,20);
       printf("U\a");
       Sleep(200);
       gotoxy(34,20);
       printf("M\a");
       Sleep(200);
       gotoxy(36,20);
       printf("");
       Sleep(200);
       gotoxy(38,20);
       printf("E\a");
       Sleep(200);
       gotoxy(40,20);
       printf("L\a");
       Sleep(400);
       gotoxy(42,20);
       printf("Q\a");
       Sleep(200);
       gotoxy(44,20);
       printf("U\a");
       Sleep(200);
       gotoxy(46,20);
       printf("R\a");
       Sleep(200);
       gotoxy(48,20);
       printf("A\a");
       Sleep(200);
       printf("\n\n\n\n\n\n\n\n");
       Sleep(500);

              }


void cadre()
       {
       gotoxy(8,11);
    printf(" ษอออออออออออออออออออออออออออออออออออออออออออออออออออออออออออออออป \n");
    gotoxy(8,12);
    printf(" บ                                                               บ \n");
    gotoxy(8,13);
    printf(" บ                                                               บ \n");
    gotoxy(8,14);
    printf(" บ                                                               บ \n");
    gotoxy(8,15);
    printf(" บ                                                               บ \n");
    gotoxy(8,16);
    printf(" บ                                                               บ \n");
    gotoxy(8,17);
    printf(" บ                                                               บ \n");
    gotoxy(8,18);
    printf(" บ                                                               บ \n");
    gotoxy(8,19);
    printf(" บ                                                               บ \n");
    gotoxy(8,20);
    printf(" บ                                                               บ \n");
    gotoxy(8,21);
    printf(" บ                                                               บ \n");
    gotoxy(8,22);
    printf(" บ                                                               บ \n");
    gotoxy(8,23);
    printf(" บ                                                               บ \n");
    gotoxy(8,24);
    printf(" บ                                                               บ \n");
    gotoxy(8,25);
    printf(" บ                                                               บ \n");
    gotoxy(8,26);
    printf(" บ                                                               บ \n");
    gotoxy(8,27);
    printf(" บ                                                               บ \n");
    gotoxy(8,28);
    printf(" บ                                                               บ \n");
    gotoxy(8,29);
    printf(" บ                                                               บ \n");
    gotoxy(8,30);
    printf(" บ                                                               บ \n");
    gotoxy(8,31);
    printf(" บ                                                               บ \n");
    gotoxy(8,32);
    printf(" บ                                                               บ \n");
    gotoxy(8,33);
    printf(" บ                                                               บ \n");
    gotoxy(8,34);
    printf(" บ                                                               บ \n");
    gotoxy(8,35);
    printf(" บ                                                               บ \n");
    gotoxy(8,36);
    printf(" ศอออออออออออออออออออออออออออออออออออออออออออออออออออออออออออออออผ \n");
}

void menu1()
       {

    cadre();
    Sleep(500);gotoxy(17,8);printf("\t--- M E N U  P R I N C I P A L E ---\a");
    Sleep(500);gotoxy(16,14);printf("1)- LOGING ADMLINISTRATEUR:\a\n");Sleep(500);gotoxy(16,16); printf("2)- INSCRIPTION AUX ELECTIONS (Aministrateur):\a\n");Sleep(500);gotoxy(16,18); printf("3)- VOTER AUX ELECTION:\a");Sleep(500);gotoxy(16,20);printf("4)- Voir les statistiques:\a");Sleep(500);gotoxy(16,22); printf("5)- QUITTER:\a\n");Sleep(500);gotoxy(15,26);printf(" VOTRE CHOIX SVP:\a\n");

       char cod;
       gotoxy(40,26);
       //getchar();
       cod=getchar();

             switch(cod)

              {
                     case '1':
                            {      gotoxy(14,26);
                                   Taper_Mot_Passe();
                                   menu_admin();
                            }break;

                     case '2':
                            {      gotoxy(15,32);
                                    getchar();
                                   Taper_Mot_Passe();
                                   sinscrir_o_elections();
                                    menu1();
                            }break;
                     case '3':
                            {
                                   gotoxy(10,32);
                                    getchar();
                                  test_exitence_par_code();
                                   getch();
                                   printf("taper une touche pour continuer");
                                   system("cls");
                                    menu1();

                            }break;

                     case '4':
                            {             printf("\n\n\n\n\n\n");
                                          exit(0);
                            }break;

                     default :
                            {
                               gotoxy(11,32);
                               printf("Desole votre proposition ne figure ps ds la liste des choix.\n\n\n\n");
                               gotoxy(17,34);
                               printf("ok taper une touche pr continuer");
                               getch();
                               system("cls");
                               menu1();
                            }break;
              }



    }


void gotoxy(int x, int y)
       {
                       COORD coord;
                       coord.X = x;
                       coord.Y = y;
                       SetConsoleCursorPosition(GetStdHandle(STD_OUTPUT_HANDLE), coord);
       }




void menu_admin()
       {
              char i;
              cadre();
              gotoxy(19,8);
              printf("-- Mr.  L ' A D M I N I S T R A T E U R --\a");Sleep(300);gotoxy(16,14);printf("1)- AFFICHER LA LISTE DES ADHERENTS:\a");Sleep(500);gotoxy(16,16);printf("2)- AFFICHER LE NOMBRE DES ADHERENTS:\a");Sleep(500);gotoxy(16,18); printf("3)- AJOUTER UN ADHERENT:\a");Sleep(500);gotoxy(16,20); printf("4)- SUPPRIMER UN ADHERENT PAR NOM:\a");Sleep(500);gotoxy(16,22); printf("5)- CHERCHER UN AHERENT PAR CODE:\a");Sleep(500);gotoxy(16,24); printf("6)- QUITTER:\a");Sleep(500);gotoxy(16,26);printf("-- VOTRE CHOIX SVP :\n\a");
              gotoxy(40,26);
              getchar();
              scanf("%c",&i);

   switch(i)
    {
            case '1' : {
                           // gotoxy(10,32);
                            system("cls");
                            printf("Adhesion   | Nom   | Prenom   | Adresse    | Email    | Ville    | Age    | Institution_de_tutelle | Fct_ds_Institution\n\n");
                            afficher_adherents();
                            printf("\n\t\tok taper une touche pr revenir au menu admin");
                            getch();
                            system("cls");
                            menu_admin();

                            } break;
            case '2' : {
                            gotoxy(17,32);
                            printf("Le nombre des adherents a l\'association est :%d ",afficher_nbre_adherents());
                            gotoxy(18,34);
                            printf("ok taper une touche pr continuer");
                            getch();
                            system("cls");
                            menu_admin();
                            } break;
            case '3' : {
                            gotoxy(17,32);
                            system("cls");
                            ajouter_adherent();
                            gotoxy(18,34);
                            printf("ok taper une touche pr continuer");
                            getch();
                            system("cls");
                            menu_admin();
                            } break;
            case '4' : {

                            gotoxy(17,32);
                            supprimer_adherent();
                            gotoxy(17,32);
                            printf("ok c\' fait s\'il existe, taper une touche pr continuer");
                            getch();
                            system("cls");
                            menu_admin();
                            }  break;
            case '5' : {

                            gotoxy(17,32);
                            test_exitence();
                            gotoxy(18,34);
                            printf("ok taper une touche pr continuer");
                            getch();
                            system("cls");
                            menu_admin();
                            } break;
            case '6' : {
                            system("cls");
                            menu1();
                            } break;

           default :  {

                            gotoxy(17,32);
                            printf("\n\nDesole votre proposition ne figure pas dans la liste des choix.\n\n\n\n");
                            gotoxy(18,34);
                            printf("ok taper une touche pr continuer");
                            getch();
                            system("cls");
                            menu_admin();
                            }break;
    }
       printf("\n\n\n\n\n");
       }


int main ( int argc , char* argv[] )
       {

                     int i;


              intro1();
             // Sleep(2000);
              intro2();
              menu1();
             // menu_admin();






       printf("\n\n\n\n\n\n");

     return 0;
       }


