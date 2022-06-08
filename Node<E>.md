public class Node<E> {
    private E data;
    private Node<E> next;
    
     /**
     * Constructors 
     * @param initialData The initial data for the Node<E>.
     * @param initialNext The initial link for the Node<E>.
     */
    public Node(E initialData, Node<E> initialNext)
    {
        this.data=initialData;
        this.next=initialNext;
    }
    /**
     * getData method returns the data.
     * @return the data from Node<E>.
     */
    public E getData()
    {
        return this.data;
    }
    
     /**
     * getNext method returns the next.
     * @return the next from the Node<E>.
     */
    public Node<E> getNext()
    {
        return this.next;
    }
    
    /**
     * setData method modifies the newData.
     * @param newData updates the newData for Node<E>.
     */
    public void setData (E newData)
    {
        this.data=newData;
    }
    
    /**
     * setNext method modifies the newNext.
     * @param newNext updates the newLink for Node<E>.
     */
    public void setNext(Node<E> newNext)
    {
        this.next=newNext;
    }

}
