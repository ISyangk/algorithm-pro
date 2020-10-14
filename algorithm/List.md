## 实现一个链表
    ```function Node(el) {
        this.element = el;
        this.next = null;
    }

    function LList() {
        this.head = new Node("head");
        this.find = find;
        this.findPre = findPre;
        this.insert = insert;
        this.display = display;
        this.remove= remove;
    }

    function find(item){
        var currentNode = this.head;
        while(currentNode.element != item){
            currentNode = currentNode.next;
        }
        return currentNode;
    }

    function insert(newElement, item) {
        var newNode = new Node(newElement);
        var current = this.find(item);
        newNode.next = current.next;
        current.next = newNode;
    }

    function display(){
        var currNode = this.head;
        while(!(currNode.next == null)){
            console.log(currNode.next.element);
            currNode = currNode.next;
        }
    }

    function findPre(item){
        var currNode = this.head;
        while (currNode.next.element != item){
            currNode = currNode.next
        }
        return currNode;
    }

    function remove(item) {
        var current = this.findPre(item);
        current.next = item.next;
    }

    var cities = new LList();
    cities.insert("Beijing", "head");
    cities.insert("Shanghai","Beijing");
    cities.remove('Shanghai');
    cities.display();
    ```