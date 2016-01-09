# InsertionSort
This program uses Inheritance and insertion sort to sort an array of integers.

public class IntList {
    protected int[] list;
    protected int numElements = 0;
public IntList(int size) {
    list = new int[size];
}

public void add(int value){
    if (numElements == list.length)
        System.out.println("Can't add, list is full");
    else {
        list[numElements] = value;
        numElements++;
    }
}

public String toString(){
    String returnString = "";
    for (int i=0; i<numElements; i++)
    returnString += i + ": " + list[i] + "\n";
    return returnString;
    }    
}
----------------------------------------------------------------------

public class SortedIntList extends IntList {
public SortedIntList(int size){
    super(size);
    }
public void add(int value){
    
    if (numElements == 0){
        list[0] = value;
        numElements++;
    }

    else if (numElements == list.length){
        System.out.println("Can't add, list is full");
    }   
    
    else if (numElements > 0 && numElements != list.length) {
        
        int position = 0;
        int totalNum = numElements;
        for(int c=0; list[c] <= value && c <= numElements; c++){
            position = c;
        }
        if (list[position] != 0){
            while (totalNum >= position){
               list[totalNum+1] = list[totalNum] ;
               totalNum--;
            }
            list[position] = value;
            numElements++;
        }
        else {
            list[numElements] = value;
            numElements++;
        }
           
    }
}
}
-------------------------------------------------------------------

public class ListTest{

    public static void main(String[] args){
        SortedIntList myList = new SortedIntList(10);
        myList.add(100);
        myList.add(50);
        myList.add(200);
        myList.add(25);
        System.out.println(myList);
    }
}
   
