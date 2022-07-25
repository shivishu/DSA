# DSA
public class Main
{ 
    Node head;
    class Node{
        String data;
        Node next;
        
        Node(String data){
            this.data=data;
            this.next=null;
        }
    }
    public void addFirst(String data){
        Node newNode = new Node(data);
        if(head==null){
            head=newNode;
            return;
        }
        newNode.next=head;
        head=newNode;
        
    }
    public void addLast(String data){
        Node newNode = new Node(data);
        if(head==null){
            head=newNode;
            return;
        }
        Node currNode=head;
        while(currNode.next !=null){
            currNode=currNode.next;
        }
        currNode.next=newNode;
    }
    public void printList(){
        
        if(head==null){
            System.out.println("empty");
            return;
        }
        Node currNode=head;
        while(currNode !=null){
            System.out.print(currNode.data+"-->");
            currNode=currNode.next;
        }
        System.out.println("null");
        
    }
	public static void main(String[] args) {
	    Main ll = new Main();
	    ll.addFirst("is");
	    ll.addFirst("a");
	    ll.addFirst("this");
	    ll.addLast("list");
	    ll.printList();
	    
	    

	}
}
# BINARY SEARCH TREE OPRATIONS
public static boolean search(Node root,int key){
    if(root==null){
        return false;
    }
    if(key==root){
        return true;
    }
    else if(root.data>key){
       return search(root.left,key);
    }
    else{
       return search(root.right,key);
    }
}
	public static void main(String[] args) {
	    int[] values={1,7,3,2,6,5};
	    Node root=null;
	    for(int i =0; i<values.length; i++){
	        root=insert(root,values[i]);
	    }
	    inorder(root);
	    System.out.println();
		
	}
	if(search(root,7)){
	    System.out.println("found");
	    
	    
	}
	else{
	    System.out.println("not found");
	}
}
#DELETE OP IN BST
class GFG {


    static class Node{
    int data;
    Node left;
    Node right;
    Node(int data){
        this.data=data;
    }
}
public static Node insert(Node root,int val){
    if(root==null){
        root = new Node(val);
        return root;
    }
    if(root.data>val){
   root.left= insert(root.left,val);
}
else{
    root.right=insert(root.right,val);
}
return root;
}

public static void inorder(Node root){
    if(root==null){
        return ;
    }
    inorder(root.left);
    System.out.print(root.data +" ");
    inorder(root.right);
}
public static boolean search(Node root,int key){
    if(root==null){
        return false;
    }
   
     if(root.data>key){
        return search(root.left,key);
    }
    else if (root.data<key){
       return  search(root.right,key);
    }
    else {
        return true;
    }
}
public static Node delete(Node root,int val){
    if(root.data>val){
        root.left=delete(root.left,val);
    }
    else if(root.data<val){
        root.right=delete(root.right,val);
    }
    else{
        if(root.left==null&&root.right==null){
            return null;
        }
        if(root.left==null){
            return root.right;
        }
        else if(root.right==null){
            return root.left;
        }
        Node IS=inorderSuccessor(root.right);
        root.data=IS.data;
       root.right= delete(root.right,IS.data);
    }
    return root;
}
public static Node inorderSuccessor(Node root){
    while(root.left !=null){
        root=root.left;
    }
    return root;
    
}
	public static void main(String[] args) {
	    int[] values={1,7,3,2,6,5};
	    Node root=null;
	    for(int i =0; i<values.length; i++){
	        root=insert(root,values[i]);
	    }
	    inorder(root);
	    System.out.println();
		
	delete(root,3);
	inorder(root);
}
}
