import java.util.*;
class tree1{
	
	static Scanner sc= null;
	public static void main(String strr[]){
		
		sc=new Scanner(System.in);
		Node root=createTree();
		inOrder(root);
		System.out.println();
		preOrder(root);
		System.out.println();
		postOrder(root);
		System.out.println();
	}
static Node createTree(){
	Node root=null;
	System.out.println("Enter Data");
	int data=sc.nextInt();
	if(data==-1){
		return null;
	}
	root =new Node(data);
	System.out.println("Enter Data for left node"+data);
	root.left=createTree();
	System.out.println("Enter Data for right node"+data);
	root.right=createTree();
	return root;
}	
	static void inOrder(Node root){
		if(root==null){
			return;
		}
		inOrder(root.left);
		System.out.print(root.data+" ");
		inOrder(root.right);	
	}
	static void preOrder(Node root){
		if(root==null){
			return;
		}
		System.out.print(root.data+" ");
		preOrder(root.left);
		preOrder(root.right);	
	}
	static void postOrder(Node root){
		if(root==null){
			return;
		}
		postOrder(root.left);
		postOrder(root.right);	
		System.out.print(root.data+" ");
	}
}
	class Node{
		Node left,right;
		int data;
		public Node(int data){
			this.data=data;
			
		}
	}
