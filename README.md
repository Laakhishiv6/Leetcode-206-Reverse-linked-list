# Leetcode-206-Reverse-linked-list

# Description
]Given the head of a singly linked list, reverse the list, and return the reversed list.
# Solution
Reversing a linked list is similar to reversing a normal list of arrays or any other elements.

The only difference with linked lists is that it works with pointers , hence we have to be careful while reversing the linked list.
![IMG_9466](https://github.com/user-attachments/assets/253c259d-3818-4414-93d0-d8520a681ebb)
![IMG_9467](https://github.com/user-attachments/assets/2837df5a-d44a-465b-a95b-1d8e8972489e)


We initially created a pointer named curr which points at the head of the linked list . Now in order to reverse the linked list we have to point the curr to its prev position and hence we will be doing the same with all the elements . In this way each element will be pointing to its previous position which will create a reverse linked list.

BUT BUT BUT its not so easy to do this because if we point the curr to prev position we might lose the rest of elements as we have lost the connection between the current pointer and the next all elements .

To solve this issue we can create a temp pointer which points to the next of current pointer , in this way we wont be able to lose the elements while reversing and hence can keep the track of the rest of the elements as well.

# Algorithm
1. Create a prev pointer which points initially to None or Null.
2. Create a curr pointer which initially points to head of the linked list.
3. Use a while loop until the curr becomes None.
4. Inside of the loop . Create a temp pointer to keep track the elements and points to the next of curr.
5. Now reverse the curr pointer to prev position.
6. In order to move forward and reverse the rest of the linked list , point the prev to curr.
7. And point curr to the temp
8. Keep on doing this operation till the curr becomes None
9. Return the head .
# Code
class Solution:

    def reverseList(self, head: Optional[ListNode]) -> Optional[ListNode]:
        prev=None
        curr=head
        while(curr!=None):
            temp=curr.next
            curr.next=prev
            prev=curr
            curr=temp
        
        return prev
# Time complexity
The algorithm traverses the entire linked list once.

Each node is visited exactly one time, and operations on each node are constant time.

Time Complexity: O(n)
Where n is the number of nodes in the linked list.
