# Hardy-Ramanujan-Numbers
''

#include <stdio.h>


struct node{
    int key;
    int d1;
    int d2;
    int i1;
    int y1;
    struct node *next;};

struct node *head = NULL;

void insertFirst(int k,int d1,int d2,int i1,int y1){
    struct node *temp = (struct node*)malloc(sizeof(struct node));

    temp->key = k;
    temp->d1 = d1;
    temp->d2 = d2;
    temp->i1 = i1;
    temp->y1 = y1;
    temp->next = head;

    head = temp;}

void printList()
{
    struct node *ptr = head;

    while(!(ptr==NULL)){
        printf("%d\t%d^3 + %d^3||%d^3+%d^3\n", ptr->key,ptr->d1,ptr->d2,ptr->i1,ptr->y1);
        ptr = ptr->next;
    }
}

int find(int k)
{
    struct node *ptr = head;

    while(!(ptr==NULL))
    {
        if(ptr->key == k)
        {
            return 1;
        }
        ptr = ptr->next;
    }

    return -1;
}


int main()
{

    int swapi,swapy;
    int i1=0,y1=0;
	int i,y,z;
	int on = 48;
	int d=100;
	int deger=100000;
	int sonuc ;

    do
    {
        i=1;
        z=0;

        do
        {

            y=1;
            do
            {

				sonuc = (i*i*i)+(y*y*y);
				if(d == sonuc )
				{
					z++	;

					i1= i;
                    y1=y;

                    
				}

				if(z==3)
                {

                    if(i1 != i && y1 != y )
                    {
                        if(find(d) == -1)
                        {

                            insertFirst(d,i,y,i1,y1);
                        }
                    }

                }
				y++;

            }while(y<on);

            i++;
        }while(i<on);

        d++;
    }while(d < deger);

	printList();

	system("pause");
}


''
