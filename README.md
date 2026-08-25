Design your implementation of the linked list. You can choose to use a singly or doubly linked list.
A node in a singly linked list should have two attributes: val and next. val is the value of the current node, and next is a pointer/reference to the next node.
If you want to use the doubly linked list, you will need one more attribute prev to indicate the previous node in the linked list. Assume all nodes in the linked list are 0-indexed.

Implement the MyLinkedList class:

MyLinkedList() Initializes the MyLinkedList object.
int get(int index) Get the value of the indexth node in the linked list. If the index is invalid, return -1.
void addAtHead(int val) Add a node of value val before the first element of the linked list. After the insertion, the new node will be the first node of the linked list.
void addAtTail(int val) Append a node of value val as the last element of the linked list.
void addAtIndex(int index, int val) Add a node of value val before the indexth node in the linked list. If index equals the length of the linked list, the node will be appended to the end of the linked list. If index is greater than the length, the node will not be inserted.
void deleteAtIndex(int index) Delete the indexth node in the linked list, if the index is valid.


public MyLinkedList() {
   class MyLinkedList {
       
        //Node class
        class Node {        
            int data = data;
            Node next = null;

            Node(int data){
                this.data = data;
                this.next = null
            }
        }
        Node head; 
        int size;

        //constructor
        public MyLinkedList(){
            head = null;
            size = 0;
        }
        // get value at index
        public int get(int index){
             if(index < 0 || inedx>=size){
                 return -1;
            }
            Node current = head;
                for(int i = 0; i<index; i++){
                    current = current.next;
                }
                return current.data;
            }
            //add node at head
            public void addAtHead(int data){
                Node newNode = new Node(data);

                newNode.next = head;
                head = newNode;

                size++;
            }
            //add node at tail
            public void addAtTail(int data){
                Node newNode = new Node(data);

                if(head == null){
                    head = newNode;
                    size++;
                    return;
                }

                Node current = head;

                while(current.next != null){
                    current = current.next;
                }
                current.next = newNode;
                size++;

            }
            //add node at given index
            public void addAtIndex(int index, int data){
                if(index < 0 || index >size){
                    return;
                }
                //if adding at head
                if(index == 0){
                    addAtHead(data);
                    return;
                }
                //if adding at tail
                if(index == size){
                    addAtTial(data);
                    return;
                }

                Node newNode = new Node(data);
                Node current = head;

                //reach node just before index
                for(int i = 0; i < index - 1; i++){
                    current = current.next;
                }

                newNode.next = current.next;
                current.next = newNode;
                size++;
            }
            //delete node at index
            public void deletAtIndex(int index){
                if(index < 0 || index == size){
                    return;
                
                }
                //delete head
                if(index == 0){
                    head = head.next;
                    size--;
                    return;
                
                }
                Node current = head;

                //reach node just before the node to delete
                for(int i = 0 ; i < index - 1; i++){
                    current = current.next;
    
                }
                current.next = current.next.next;
                size--;
            }
        }
    }
    


/**
 * Your MyLinkedList object will be instantiated and called as such:
 * MyLinkedList obj = new MyLinkedList();
 * int param_1 = obj.get(index);
 * obj.addAtHead(val);
 * obj.addAtTail(val);
 * obj.addAtIndex(index,val);
 * obj.deleteAtIndex(index);
 */
