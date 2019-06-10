#include <string>
#include <iostream>
#include <string.h>
#include <fstream>
#include <sstream>
#include <algorithm>
using namespace std;




template <class x>
class node
{
public:
	x english;
	x turkish;
	node *left = NULL;
	node *right = NULL;

};
template <class x>
class BT               // binary tree
{
public:
	void insert(x newword,x newtrans);
	node<x>* search(x key);
	void newtrans(x word , x newtrans);
	void newword();
	node<x> * root = NULL;




};
template <class x>
void BT<x>::insert(x newword, x newtrans)
{
	
	node<string> *temp = new node<string>;
	
	temp->english = newword;
	temp->turkish = newtrans;

	if (root == NULL)
	{
		root = temp;

	}
	else if (root != NULL)
	{
		node<string>* temproot = new node<string>;
		temproot = root;
		while (temproot !=NULL)
		{
			if (newword < temproot->english )
			{
				if (temproot->left == NULL)
				{
					temproot->left = temp;
					break;
				}
				temproot = temproot->left;
			}
			else if (newword > temproot->english)
			{
				if (temproot->right == NULL)
				{
					temproot->right = temp;
					break;
				}
				temproot = temproot->right;
			}
			else if (newword == temproot->english)
			{
				/*cout << "this word already exist" << endl;*/
				break;
			}
		}
		
		
	}
}
template <class x>
node<x>* BT<x>::search(x key)
{
	bool a = false;
	node<string> * current = new node<string>;
	current = root;
	/*cout << "visiting nodes : " << endl;*/
	while (current != NULL && current->english != key)
	{
		if (current != NULL)
		{
			/*cout << current->english << endl;*/
			if (key <= current->english)
			{
				current = current->left;
			}
			else if (key >= current->english)
			{
				current = current->right;
			}
		}
		
		
	}
	if (current == NULL)
	{
		a = true;
		/*cout << "no element in tree" << endl;*/
		return 0;

	}
	if (!a)
	{
		return current;
	}
	

}
template <class x>
void BT<x>::newword()
{
	cout << "enter new word :";
	string newword;
	cin >> newword;
	cout << endl;
	node * temp = new node;
	temp = this->search(newword);
	if (temp->english == newword);
	{
		cout << "world already exist, if you want to add new translation please use command 2" << endl;
	}
	if(temp->english != newword)
	{
		cout << "Enter new translation :";
		string trans;
		cin >> trans;
		cout << endl;
	}
}
template <class x>
void BT<x>::newtrans(x trans, x newtrans)
{
	node<string> * temp = new node<string>;
	temp = search(trans);
	temp->turkish = newtrans;
	cout << endl;
	cout << "**UPDATED**";
	cout << endl;
}


int main()
{
	BT<string> binarytree;
	ifstream file;
	file.open("dict.txt");
	string line;
	while (getline(file,line))
	{
		
		string final;
		istringstream ikra(line);
		string eng;
		string tr;
		ikra >> eng;
		std::transform(eng.begin(), eng.end(), eng.begin(), ::tolower);
		while (ikra >> tr)
		{
			if (tr != "")
			{
				final = final + tr + " ";
			}
		}
		if (eng != "")
		{
			binarytree.insert(eng, final);
		}
		
	}

	
	cout << "Query: 1" << endl;
	cout << "Add new Translation: 2" << endl;
	cout << "Add new word: 3" << endl;
	cout << "Exit : 0 " << endl;
	while (1)
	{
		string userchoice;
		cout << "Enter Command : ";
		cin >> userchoice;
		if (userchoice == "1")
		{
			node<string> * temp = new node<string>;
			string a;
			cout << "Enter queried word :";
			cin >> a;
			temp = binarytree.search(a);
			if (temp != NULL)
			{
				cout <<   temp->english  + " --------->> "+ temp->turkish << endl;
			}
			else
			{
				cout << "this word not in dictionary!!!" << endl;
			}
			
		}
		else if (userchoice == "2")
		{
			node<string>* temp = new node<string>;
			string newtrans;
			string eng;
			cout << "which word do you want to edit : ";
			cin >> eng;
			temp = binarytree.search(eng);
			
			if (temp == NULL)
			{
				cout << "this word not in the dictionary , you can add it with command 3" << endl;
			}
			else
			{
				cout << "Enter the new translation :";
				cin >> newtrans;
				binarytree.newtrans(eng, newtrans);
			}

			
		}
		else if (userchoice == "3")
		{
			node<string> * temp = new node<string>;
			string newword;
			string newtrans;
			cout << "enter new word :";
			cin >> newword;
			
			temp = binarytree.search(newword);
			if (temp != NULL && temp->english == newword)
			{
				cout << "this word already in dictionary" << endl;
			}
			else
			{
				cout << "enter translation :";
				cin >> newtrans;
				binarytree.insert(newword , newtrans);
			}
			
				
		}
		else if (userchoice =="0")
		{
			break;
		}
		else
		{
			cout <<"-----------Wrong command , try again!!!-------------" << endl;
			cout << endl;
		}
	}





	/*cout << binarytree.search("way")->turkish;
	cin.get();
	cin.ignore();*/
	
	return 0;
}
