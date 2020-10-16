## 实现一个链表
    ```js
    // 节点构造函数
    function Node(el) {
        this.element = el;
        this.next = null;
    }
    // 链表类
    function LList() {
        this.head = new Node("head");
        this.find = find;
        this.findPre = findPre;
        this.insert = insert;
        this.display = display;
        this.remove= remove;
    }
    // 查找节点方法
    function find(item){
        var currentNode = this.head;
        while(currentNode.element != item){
            currentNode = currentNode.next;
        }
        return currentNode;
    }
    // 插入节点方法
    function insert(newElement, item) {
        var newNode = new Node(newElement);
        var current = this.find(item);
        newNode.next = current.next;
        current.next = newNode;
    }
    // 打印所有节点
    function display(){
        var currNode = this.head;
        while(!(currNode.next == null)){
            console.log(currNode.next.element);
            currNode = currNode.next;
        }
    }
    // 查找节点的上一个节点
    function findPre(item){
        var currNode = this.head;
        while (currNode.next.element != item){
            currNode = currNode.next
        }
        return currNode;
    }
    // 删除节点
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