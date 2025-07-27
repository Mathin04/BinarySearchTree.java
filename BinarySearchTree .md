public class BinarySearchTree {



    static class Node {

        int key;

        Node left, right;



        public Node(int item) {

            key = item;

            left = right = null;

        }

    }



    Node root;



    BinarySearchTree() {

        root = null;

    }



    void insert(int key) {

        root = insertRec(root, key);

    }



    Node insertRec(Node root, int key) {

        if (root == null) {

            root = new Node(key);

            return root;

        }



        if (key < root.key)

            root.left = insertRec(root.left, key);

        else if (key > root.key)

            root.right = insertRec(root.right, key);



        return root;

    }



    void inorder() {

        inorderRec(root);

    }



    void inorderRec(Node root) {

        if (root != null) {

            inorderRec(root.left);

            System.out.print(root.key + " ");

            inorderRec(root.right);

        }

    }



    boolean search(int key) {

        return searchRec(root, key);

    }



    boolean searchRec(Node root, int key) {

        if (root == null)

            return false;

        if (root.key == key)

            return true;

        return key < root.key ? searchRec(root.left, key) : searchRec(root.right, key);

    }



    void deleteKey(int key) {

        root = deleteRec(root, key);

    }



    Node deleteRec(Node root, int key) {

        if (root == null)

            return root;



        if (key < root.key)

            root.left = deleteRec(root.left, key);

        else if (key > root.key)

            root.right = deleteRec(root.right, key);

        else {



            if (root.left == null)

                return root.right;

            else if (root.right == null)

                return root.left;



            root.key = minValue(root.right);

            root.right = deleteRec(root.right, root.key);

        }



        return root;

    }



    int minValue(Node root) {

        int minv = root.key;

        while (root.left != null) {

            minv = root.left.key;

            root = root.left;

        }

        return minv;

    }



    public static void main(String\[] args) {

        BinarySearchTree bst = new BinarySearchTree();



        bst.insert(50);

        bst.insert(30);

        bst.insert(20);

        bst.insert(40);

        bst.insert(70);

        bst.insert(60);

        bst.insert(80);



        System.out.println("Inorder traversal:");

        bst.inorder();



        System.out.println("\\nSearch 40: " + bst.search(40));

        System.out.println("Search 90: " + bst.search(90));



        System.out.println("Deleting 20");

        bst.deleteKey(20);

        bst.inorder();



        System.out.println("\\nDeleting 30");

        bst.deleteKey(30);

        bst.inorder();



        System.out.println("\\nDeleting 50");

        bst.deleteKey(50);

        bst.inorder();

    }

}



    static class Node {

        int key;

        Node left, right;



        public Node(int item) {

            key = item;

            left = right = null;

        }

    }



    Node root;



    BinarySearchTree() {

        root = null;

    }



    void insert(int key) {

        root = insertRec(root, key);

    }



    Node insertRec(Node root, int key) {

        if (root == null) {

            root = new Node(key);

            return root;

        }



        if (key < root.key)

            root.left = insertRec(root.left, key);

        else if (key > root.key)

            root.right = insertRec(root.right, key);



        return root;

    }



    void inorder() {

        inorderRec(root);

    }



    void inorderRec(Node root) {

        if (root != null) {

            inorderRec(root.left);

            System.out.print(root.key + " ");

            inorderRec(root.right);

        }

    }



    boolean search(int key) {

        return searchRec(root, key);

    }



    boolean searchRec(Node root, int key) {

        if (root == null)

            return false;

        if (root.key == key)

            return true;

        return key < root.key ? searchRec(root.left, key) : searchRec(root.right, key);

    }



    void deleteKey(int key) {

        root = deleteRec(root, key);

    }



    Node deleteRec(Node root, int key) {

        if (root == null)

            return root;



        if (key < root.key)

            root.left = deleteRec(root.left, key);

        else if (key > root.key)

            root.right = deleteRec(root.right, key);

        else {



            if (root.left == null)

                return root.right;

            else if (root.right == null)

                return root.left;



            root.key = minValue(root.right);

            root.right = deleteRec(root.right, root.key);

        }



        return root;

    }



    int minValue(Node root) {

        int minv = root.key;

        while (root.left != null) {

            minv = root.left.key;

            root = root.left;

        }

        return minv;

    }



    public static void main(String\[] args) {

        BinarySearchTree bst = new BinarySearchTree();



        bst.insert(50);

        bst.insert(30);

        bst.insert(20);

        bst.insert(40);

        bst.insert(70);

        bst.insert(60);

        bst.insert(80);



        System.out.println("Inorder traversal:");

        bst.inorder();



        System.out.println("\\nSearch 40: " + bst.search(40));

        System.out.println("Search 90: " + bst.search(90));



        System.out.println("Deleting 20");

        bst.deleteKey(20);

        bst.inorder();



        System.out.println("\\nDeleting 30");

        bst.deleteKey(30);

        bst.inorder();



        System.out.println("\\nDeleting 50");

        bst.deleteKey(50);

        bst.inorder();

    }

}

