# Singly-LinkList
Addlast and Display with user Input

import java.util.Scanner;

public class LinkdListProg {
    Node head, tail;
    static Scanner sc = new Scanner(System.in);

    class Node {
        int data;
        Node next;

        Node(int data) {
            this.data = data;
            this.next = null;
        }
    }

    // add
    void addLast(int data) {
        Node newNode = new Node(data);
        if (head == null) {
            head = newNode;
            tail = newNode;
            return;
        }
        tail.next = newNode;
        tail = newNode;
        // tail.next = head;
    }

    void display() {
        if (head == null) {
            System.out.println("Node is empty");
            return;
        }
        Node curNode = head;
        do {
            System.out.print(curNode.data);
            System.out.print(" -> ");
            curNode = curNode.next;
        } while (curNode != head);
    }

    public static void main(String[] args) {
        LinkdListProg ll = new LinkdListProg();
        System.out.println("Press -1 To stop");
        while (true) {
            System.out.print("Enter Data : ");
            int data = sc.nextInt();
            if (data == -1) {
                break;
            }
            ll.addLast(data);
        }
        ll.display();
    }
}
