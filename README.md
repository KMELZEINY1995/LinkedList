# LinkedList

public class LinkedList {

	private Node top;  // point to the head of the list
	private int size; // the size of the LinkedList
	/**
	 * LinkedList.
	 * Constructor of the linked list class
	 * PARAMETERS:
	 *    N/A
	 * RETURNS:
	 *    N/A
	 */
	public LinkedList() {
		top = null;
		size = 0;
	}
	/**
	 * INSERT(Object theItem)
	 *
	 * PARAMETERS:
	 *      Object TheItem to insert in liked List
	 * 
	 * RETURNS:
	 *    doesn't return anything
	 *    	 */
	
	public void insert(Object theItem) {
		if(top == null)
		{
			top = new Node(theItem);
		}else
		{
		 top = new Node(theItem , top);
		 size++;
		}
	}
	/**
	 * Delete(Object theItem)
	 *
	 * it delete the first instance of the Object
	 * PARAMETERS:
	 *     Object theItem 
	 *     
	 * RETURNS:
	 *    Reference of the deleted item 
	 */
	public Object delete(Object theItem)
	{
		Node curr = top;
		Node prev = null;
		while (curr != null) {		
			if (theItem.equals(curr.item)) {
				if (prev == null) {
					top = curr.next;
				} else {
					prev.next = curr.next;
				}
				size--;
			} else {
				prev = curr;
			}
			curr = curr.next;
		}
		return theItem;
	}
	/**
	 * LinkedList reverse()
	 * 
	 * it create a new linked list and use the private method to reverse a function
	 * PARAMETERS:
	 *    N/A
	 * RETURNS:
	 *    The new reversed linked list
	 */
	public LinkedList reverse() {
		LinkedList newOne = new LinkedList();
		Node newTop = top;
	    reverseRecsively(newOne , newTop);
		return newOne;
	}
	/**
	 * reverseRecsively(LinkedList newOne , Node curr)
	 *
	 *reverse linked list recsively  
	 * PARAMETERS:
	 *    Linked list newOne  : pass the list that add items it
	 *    Node curr : pass pointer to the top item
	 * RETURNS:
	 *    what is the meaning of the return value?
	 */
	private void reverseRecsively(LinkedList newOne , Node curr) {
		if (curr == null)
		{
			return;
		}else
		{
		newOne.insert(curr.item);
		curr = curr.next;
		reverseRecsively(newOne , curr);
	 }
}
	/**
	 * Describe the purpose of the method. Clearly.
	 *
	 * PARAMETERS:
	 *    firstParam  description of what firstParam
	 *                means; if it is a reference, and
	 *                its value is modified, discuss
	 *    secondParam description of secondParam (as
	 *                above)
	 *
	 * RETURNS:
	 *    what is the meaning of the return value?
	 */
	public int getSize() {
		return size;
	}
	/**
	 * Describe the purpose of the method. Clearly.
	 *
	 * PARAMETERS:
	 *    firstParam  description of what firstParam
	 *                means; if it is a reference, and
	 *                its value is modified, discuss
	 *    secondParam description of secondParam (as
	 *                above)
	 *
	 * RETURNS:
	 *    what is the meaning of the return value?
	 */
	public Object initTraversal() {
		Node head = top;
		if (head == null) {
			return null;
		} else {
			return head.item;
		}
	}
	/**
	 * Describe the purpose of the method. Clearly.
	 *
	 * PARAMETERS:
	 *    firstParam  description of what firstParam
	 *                means; if it is a reference, and
	 *                its value is modified, discuss
	 *    secondParam description of secondParam (as
	 *                above)
	 *
	 * RETURNS:
	 *    what is the meaning of the return value?
	 */
	public Object traverse() {
		if (top.next == null) {
			return null;
		} else {
			top = top.next;
			return top.item;
		}
	}
	
	/**
	 * ToString
	 *     
	 *   print all the nodes in linked list 
	 * PARAMETERS:
	 * N/A
	 * RETURNS:
	 *    The String that have all the nodes
	 */
	public String toString() {
		String result = "{";
		Node head = top;
		while (head.next != null) {
			result += head.item + ";";
			head = head.next;
		}
		return  result + "}";
	}
	/**
	 * Describe the purpose of the method. Clearly.
	 *
	 * PARAMETERS:
	 *    firstParam  description of what firstParam
	 *                means; if it is a reference, and
	 *                its value is modified, discuss
	 *    secondParam description of secondParam (as
	 *                above)
	 *
	 * RETURNS:
	 *    what is the meaning of the return value?
	 */
	
	private void printComma(int x) {
		if (x == 0) {
			return;
		} else {
			if(x > 0)
			{	
			System.out.print(";");
			
			}
			 printComma(x - 1);
		}
	}

}

class Node {
	 Node next;
	 Object item;
	 /**
	  * Nodes
	  *Constructor of Node class
	  * PARAMETERS:
	  *    Object item
	  *    Node next 
	  * RETURNS:
	  *    N/A
	  */
	public Node(Object item, Node next) {
		this.item = item;
		this.next = next;
	}
	/**
	  * Nodes
	  *Constructor of Node class
	  * PARAMETERS:
	  *    Object item 
	  * RETURNS:
	  *    N/A
	  */
	public Node(Object item)
	{
		this.item = item;
		this.next = null;
	}
}
