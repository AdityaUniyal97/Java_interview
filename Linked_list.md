**Linked List is a sequence of Nodes where each node contains data and a pointer to the next node.**
**Advatnage= Dynamic Size , easy insert and delete**
**Disadvantage = No random access , extra memory for pointer**

# Insert at Begining
```
public Node insertAtBegin(Node head , int x){
        Node temp = new Node(x);
        if(head == null){
            return temp;
        }
        temp.next = head;
        head = temp;
        return head;
    }
```
# Insert at the end Single Linked List
```
static Node insert(Node head , int x){
        Node temp = new Node(x);
        if(head == null){
            return temp;
        }
        Node curr = head;
        while(curr.next != null){
            curr = curr.next;
        }
        curr.next = temp;
        return head;
    }
```

# Insert at Position in Single Linked List
```
Node insertAtPos(Node head , int x , int pos){
        Node temp = new Node(x);
        if(head == null){
            if(pos  == 1){
                return temp;
            }
            else{
                return head;
            }
        }
        if(pos == 1){
            temp.next = head;
            return temp;
        }
        Node curr = head;
        for(int i =  1; i < pos - 1 ; i++){
            curr = curr.next;
            if(curr == null){
                System.out.println("Postion out of Range");
                return head;
            }
        }
        temp.next = curr.next;
        curr.next = temp;
        return head;
    }
```

# Delete from First
```
static Node Head(Node head){
        if(head == null){
            return head;
        }
        else{
            return head.next;
        }
    }
```
# Delete from last
```
static Node delHead(Node head){
        if(head == null){
            return null;
        }
        if(head.next = null){
            return null;
        }
        Node curr = head;
        while(curr.next.next != null){
            curr = curr.next;
        }
        curr.next = null;
        return head;
    }
```

# Delete from the Given Position
```
static Node deleteAtPos(Node head , int pos){
        if(head == null){
            System.out.println("List is empty");
            return head;
        }
        if(pos == 1){
            return head.next;
        }
        Node curr = head;
        for(int i = 1; i < pos - 1; i ++){
            if(curr == null || curr.next == null){
                System.out.println("Posaition out of range");
                return head;
            }
            curr = curr.next;
        }
        if(curr.next == null){
            System.out.println("Positon out of Range");
            return head;
        }
        curr.next = curr.next.next;
        return head;
    }
```

# Reverse the Singly Linked List
```
static Node reverse(Node head){
        Node prev = null;
        Node curr = head;
        while(curr != null){
            Node temp = curr.next;
            curr.next = prev;
            prev = curr;
            curr = temp;
        }
        return prev;
    }
```
# Search in the Linked List
```
static int search(Node head , int x){
        int pos = 1;
        Node curr = head;
        while(curr != null){
            if(curr.data == x){
                return pos;
            }
            else{
                pos ++;
                curr = curr.data;
            }
            
        }
        return -1;
    }
```


# DOUBLE LINKED LIST

# DLL insert at begining 
```
static Node insertAtBegin(Node head , int x){
        Node temp = new Node(x);
        temp.next = head; // if head null temp pointing to null
        if(head != null){
            head.prev = temp;
        }
        return head;
    }
```

# DLL insert at End
```
static Node insertAtEnd(Node head , int x){
        Node temp = new Node(x);
        if(head == null){
            return head;
        }
        Node curr = head;
        while(curr.next != null){
            curr = curr.next;
        }
        curr.next = temp;
        temp.prev = curr;
        return head;
    }
```

# DLL insert at Position 
```
static Node insertAtPos(Node head , int x , int pos){
        Node temp = new Node(x);
        if(pos == 1){
            temp.next = head;
            if(head != null){
                head.prev = temp;
            }
            return temp;
        }
        Node curr = head;
        for(int i = 1 ; i < pos - 1; i++){
            curr = curr.next;
        }
        if(curr == null){
            System.out.println("Out of Range");
            return head;
        }
        temp.next = curr.next;
        temp.prev = curr;
        if(curr.next != null){
            curr.next.prev = temp;
        }
        curr.next = temp;
        return head;
    }
```

# Reverse the DLL
```
static Node reverse(Node head){
        Node temp = null;
        Node curr = head;
        while(curr != null){
            temp = curr.prev;
            curr.prev = curr.next;
            curr.next = temp;
            curr = curr.prev;
        }
        if(temp != null){
            head = temp.prev;
        }
        return head;
    }
```

# Delete Head of the DLL
```
static Node delHead(Node head){
    if(head == null){
        return null;
    }
    if(head.next == null){
        return 
        head = head.next;
        head.prev = null;
        return head;
    }
}
```

# Delete the last Node of the DLL
```
=static Node lastNode(Node head){
    if(head == null){
        return null;
    }
    if(head.next == null){
        return null;
    }
    Node curr = head;
    while(curr.next != null){
        curr = curr.next;
    }
    curr.prev.next = null;
    return head;
}
```

# Delete from the Position
```
static Node deleteAtPos(Node head , int pos){
    if(head == null){
        System.out.println("List is Empty");
        return head;
    }
    if(pos <= 0){
        System.out.println("Invalid Position");
        return head;
    }
    if(pos == 1){
        Node newNode = head.next;
        if(newNode != null){
            newNode.prev = null;
        }
        return newNode;
    }
    Node curr = head;
    for(int i = 1; i < pos && curr != null ; i++){
        curr = curr.next;
    } 
    if(curr == null){
        Sytem.out.println("Postion out of Range");
        return head;
    }
    if(curr.prev != null){
        curr.prev.next  = curr.next;
    }
    if(curr.next != null){
        curr.next.prev = curr.prev;
    }
    return head;
}
```

# CIRCULAR LINKED LIST

# Insert at Begining in CLL
```
static Node insertAtBegining(Node head , int x){
    Node temp = new Node(x);
    if(head == null){
        temp.next = temp;
        return temp;
    }
    else{
        temp.next = head.next;
        head.next = temp;
        int t = head.data;
        head.data = temp.data;
        temp.data = t;
        return head;
    }
}
```