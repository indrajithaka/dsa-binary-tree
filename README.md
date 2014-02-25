dsa-binary-tree
===============

DSA project
public void InsertNode(int Isbn ,String Title, String Fname, String Lname) 
    {
       Book newNode = new Book(Isbn,Title,Fname,Lname);
        if (root == null) 
        {            
            root=newNode;
        } 
        else 
        {
            Book focusNode = root;
            Book Parent;

            while (true) 
            {
                Parent = focusNode;
                if (Isbn < focusNode.isbn) 
                {
                    focusNode = focusNode.LeftChild;
                    if (focusNode == null) 
                    {
                        Parent.LeftChild = newNode;
                        return;
                    }
                } else 
                {
                    focusNode = focusNode.RightChild;
                    if (focusNode == null) 
                    {
                        Parent.RightChild = newNode;
                        return;
                    }
                }
            }
        }
    }
  
//End of Insert Method
    
 //Find node comes here
public Book findNode(int isbn)
   {
       Book focusNode = root;
       
       while(focusNode.isbn != isbn)
       {
           if(isbn < focusNode.isbn)
           {
               focusNode = focusNode.LeftChild;

           }
           else
           {
               focusNode = focusNode.RightChild;
           }
           if(focusNode==null)
           {
               return null;
           }
          
           
       }
       return focusNode;
   }
