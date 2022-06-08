public class SinglyLinkedList<E> 
{
    private Node<E> head;
    private Node<E> tail;
    private int numElements;
   
    /**
     * No-Arg Constructor
     */
    public SinglyLinkedList()
    {
        head=null;
        tail=null;
        numElements=0;
    }
    
     /**
     * getSize method returns the size of the SinglyLinkedList.
     * @return the number of elements inside the SinglyLinkedList.
     */
    public int getSize()
    {
        return numElements;
    }
    
    /**
     * 
     * @param element adds the element into the SinglyLinkedList.
     */
    public void appendList(E newElement)
    {
         if (tail==null)
        {
            head=new Node<E>(newElement,null);
            tail=head;
        }
        else
        {
            tail.setNext(new Node<E>(newElement, null));
            tail=tail.getNext();
        }
        numElements++;
    }
    /**
     * prependList method adds a certain element to the beginning of the linked 
     *      list.
     * @param newElement the element to add to the linked list.
     */
    public void prependList(E newElement)
    {
        Node<E> newHead=new Node(newElement, head);
            if (getSize()==0)
            {
                tail=newHead;
                head=newHead;
                numElements++;
                return;
           }
           head= newHead;
           numElements++;
    }
    
    /**
     * 
     * @param target checks to see if the target exists in the SinglyLinkedList.
     * @return not successful or successful if the target is found.
     */
    public boolean exists (E target)
    {
         boolean found=false;
        Node<E> cursor=head;
        while (cursor!=null && !found)
        {
            if (cursor.getData().equals(target))
                found=true;
            else
                cursor=cursor.getNext();
        }
        return found;
    }
   
    /** 
    * @param target counts the number of occurrences of the target in
    *   the SinglyLinkedList.
    * @return the number of occurrences.
    */
    public int countOccurences(E target)
    {
           int occurrences = 0;

        for (Node<E> cursor = head; cursor != null; cursor = cursor.getNext())
        {
            if (cursor.getData().equals(target))
            {
                occurrences++;
            }
        }

        return occurrences;
    }
    
    /**
  * 
  * @param target removes the target in the SinglyLinkedList.
  * @return fail if the elements are found in the SinglyLinkedList.
  */
    public boolean remove (E target)
    {
        boolean elementFound=false;
        
        Node<E> targetNode=head;
        for (Node<E> cursor=head; cursor!=null && !elementFound; 
                cursor = cursor.getNext())
        {
            if (cursor.getData().equals(target))
            {
                elementFound=true;
                targetNode=cursor;
            }
            if(elementFound)
            {
                targetNode.setData(head.getData());
                head=head.getNext();
                numElements--;
            }
        } 
        return elementFound;
    }
    /**
     * the iterator method "copies" the linked list and passes the
     * copied linked list to a new Lister<E>
     *
     * @return a Lister<E> using a copy of the linked list
     */
    
    public Lister<E> iterator() 
    {
        // declare variables
        Node headOfListToReturn; // beginning of new "copied" list
        Node cursorOfListToCopy; // active node of list to copy
        Node lastNodeOfListToReturn; // end of new "copied" list

        // establish the copied list
        headOfListToReturn = null;

        if (head != null) {
            // create the head of the new list
            headOfListToReturn = new Node(head.getData(), null);
            // use lastNodeOfListToReturn as a pointer to the last node in the copied list
            lastNodeOfListToReturn = headOfListToReturn;
            // use currentCursor as the pointer to the existing list
            cursorOfListToCopy = head.getNext();
            // if we have a node...
            while (cursorOfListToCopy != null) {
                // create a new node from the end of the new list
                lastNodeOfListToReturn.setNext(new Node
                        (cursorOfListToCopy.getData(), null));
                // move lastNodeOfListToReturn to the new last node
                lastNodeOfListToReturn = lastNodeOfListToReturn.getNext();
                // move the cursorOfListToCopy to the next node
                cursorOfListToCopy = cursorOfListToCopy.getNext();
            }
        }

        return new Lister(headOfListToReturn);
    }
}
