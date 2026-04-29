```
#include<stdio.h>
#include<stdlib.h>
struct Node{
    int data;
    struct Node* left;
    struct Node* right;
};
struct Node* createNode(int val){
    struct Node* newNode = (struct Node*) malloc(sizeof(struct Node));
    newNode->data = val;
    newNode->left = NULL;
    newNode->right = NULL;
    return newNode;
}
struct Node* insert(struct Node* root , int val){
    if(root == NULL) return createNode(val);
    if(val < root->data){
        root->left = insert(root->left , val);
    }
    else{
        root->right = insert(root->right , val);
    }
    return root;
}
void inorder(struct Node* root){
    if(root == NULL) return;
    inorder(root->left);
    printf("%d",root->data);
    inorder(root->right);
}
void postorder(struct Node* root){
    if(root == NULL) return;
    postorder(root->left);
    postorder(root->right);
    printf("%d",root->data);
}
void preorder(struct Node* root){
    if(root == NULL) return;
    printf("%d ",root->data);
    preorder(root->left);
    preorder(root->right);
}
void search(struct Node* root , int key){
    if(root == NULL){
        printf("Not Found");
        return;
    }
    if(root->data == key){
        printf("Found");
        return;
    }
    if(key < root->data){
        search(root->left , key);
    }
    else{
        search(root->right,key);
    }
}
struct Node* findMin(struct Node* root){
    while(root->left != NULL){
        root = root->left;
    }
    return root;
}
struct Node* findMax(struct Node* root){
    while(root->right != NULL){
        root = root->right;
    }
    return root;
}
struct Node* deleteNode(struct Node* root , int key){
    if(root ==NULL) return NULL;
    if(key < root->data){
        root->left = deleteNode(root->left , key);
    }
    else if(key > root->data){
        root->right = deleteNode(root->right , key);
    }
    else{
        if(root->left == NULL && root->right == NULL){
            free(root);
            return NULL;
        }
        else if(root->left == NULL){
            struct Node* temp = root->right;
            free(root);
            return temp;
        }
        else if(root->right == NULL){
            struct Node* temp = root->left;
            free(root);
            return temp;
        }
        struct Node* temp = findMin(root->right);
        root->data = temp->data;
        root->right = deleteNode(root->right,temp->data);
    }
    return root;
}
int main(){
    struct Node* root = NULL;
    int choice , val;
    while(1){
        printf("Enter 1.Insert , 2.Inorder , 3.PostOrder , 4.PreOrder , 5.Search , 6.Delte");
        printf("Enter the Choice: ");
        scanf("%d",&choice);
        switch(choice){
            case 1: printf("Enter value ");
            scanf("%d",&val);
            root = insert(root,val);
            break;
            case 2: inorder(root);
            break;
            case 3: postorder(root);
            break;
            case 4: preorder(root);
            break;
            case 5: printf("Enter the value to search: ");
            scanf("%d",&val);
            search(root,val);
            break;
            case 6: printf("Enter the value to delete: ");
            scanf("%d",&val);
            root=deleteNode(root,val);
            break;
            case 7: exit(0);
            default: printf("Invalid");
        }
    }
}
```

## Count the Nodes having Both Childrens
```
#include<stdio.h>
#include<stdlib.h>
struct Node{
    int data;
    struct Node* left;
    struct Node* right;
};
struct Node* createNode(int val){
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = val;
    newNode->left = NULL;
    newNode->right = NULL;
    return newNode;
}
struct Node* insert(struct Node* root , int val){
    if(root == NULL) return createNode(val);
    if(val < root->data){
        root->left = insert(root->left , val);
    }
    else{
        root->right = insert(root->right,val);
    }
    return root;
}
int countNode(struct Node* root){
    if(root == NULL) return 0;
    int count = 0;
    if(root->left != NULL && root->right != NULL){
        count += 1;
    }
    return count + countNode(root->left) + countNode(root->right);
}
int main(){
    struct Node* root = NULL;
    int choice ,  val;
    while(1){
        printf("Enter the choice : 1. Insert , 2. Count the Node having both the Childs: ");
        printf("Enter the choice: ");
        scanf("%d",&choice);
        switch(choice){
            case 1: printf("Enter the  value to insertL ");
            scanf("%d",&val);
            root=insert(root,val);
            break;
            case 2: printf("%d",countNode(root));
            break;
            case 3: exit(0);
        }
    }
}
```
## Max Value in the Tree
```
int findMax(struct Node* root){
    if(root == NULL) {
        return -1;
    }
    while(root->right != NULl){
        root = root->right;
    }
    return root->right->data;
}
```

## Operations
```
#include<stdio.h>
#include<stdlib.h>
struct Node{
    int data;
    struct Node* left;
    struct Node* right;
};
struct Node* createNode(int val){
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = val;
    newNode->left = NULL;
    newNode->right = NULL;
    return newNode;
}
struct Node* insert(struct Node* root , int val){
    if(root == NULL) return createNode(val);
    if(val < root->data){
        root->left = insert(root->left , val);
    }
    else{
        root->right = insert(root->right,val);
    }
    return root;
}
int countleft(struct Node* root){
    if(root == NULL) return 0;
    int count = 0;
    if(root->left != NULL && root->right == NULL){
        count += 1;
    }
    return count + countleft(root->left) + countleft(root->right);
}
int countright(struct Node* root){
    if(root == NULL) return 0;
    int count = 0;
    if(root->left == NULL && root->right != NULL){
        count += 1;
    }
    return count + countright(root->left) + countright(root->right);
}
// count the Node on the left side of the tree
int countonleft(struct Node* root){
    if(root == NULL) return;
    return 1 + countonleft(root->left) + countonleft(right);
}

int main(){
    struct Node* root = NULL;
    int choice ,  val;
    while(1){
        printf("Enter the choice : 1. Insert , 2. Count the Node having only left child , 3> Count the Node having only right child :  ");
        printf("Enter the choice: ");
        scanf("%d",&choice);
        switch(choice){
            case 1: printf("Enter the  value to insertL ");
            scanf("%d",&val);
            root=insert(root,val);
            break;
            case 2: printf("%d",countleft(root));
            break;
            case 3: printf("%d",countright(root));
            break;
            case 4: exit(0);
        }
    }
}
```

## Count  the total Nodes in a tree
```
int countNode(struct Node* root){
    if(root == NULL){
        return 0;
    }
    return 1 + countNode(root->left) + countNode(root->right);
}
```

## Count the leaf Nodes in a tree
```
//Count the Leaf Nodes in a tree
int countLeaf(struct Node* root){
    if(root == NULL) return 0;
    if(root->left == NULL && root->right == NULL){
        return 1;
    }
    return countLeaf(root->left) + countLeaf(root->right);
}
```

## height of the Binary tree
```
//Height of the Binary tree
int height(struct Node* root){
    if(root == NULL){
        return 0;
    }
    int left = height(root->left);
    int right = height(root->right);
    return 1 + (left > right ?  left : right);
}
```

## bfs ON TREE
```
#include <stdio.h>
#include<stdlib.h>
struct Node{
    int data;
    struct Node* left;
    struct Node* right;
};
struct Node* createNode(int val){
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = val;
    newNode->left = NULL;
    newNode->right = NULL;
    return newNode;
}
struct Node* insert(struct Node* root , int val){
    if(root == NULL){
        return createNode(val);
    }
    if(val < root->data){
        root->left = insert(root->left,val);
    }
    else{
        root->right = insert(root->right , val);
    }
    return root;
}
void bfs(struct Node* root){
    if(root == NULL){
        return;
    }
    struct Node* queue[100];
    int front = 0;
    int rear = 0;
    queue[rear] = root;
    rear++;
    while(front < rear){
        struct Node* temp = queue[front];
        front++;
        printf("%d",temp->data);
        if(temp->left != NULL){
            queue[rear] = temp->left;
            rear++;
        }
        if(temp->right != NULL){
            queue[rear] = temp->right;
            rear++;
        }
    }
}
int main(){
    struct Node* root = NULL;
    int choice , val;
    while(1){
    printf("1.To Insert , 2.To Bfs");
    printf("Enter the choice: ");
    scanf("%d",&choice);
        switch(choice){
        case 1: printf("Enter the Element: ");
        scanf("%d",&val);
        root=insert(root,val);
        break;
        case 2: bfs(root);
        break;
        case 3: exit(0);
        }
    }
}
```