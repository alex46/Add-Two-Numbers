Add-Two-Numbers
===============

/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode(int x) {
 *         val = x;
 *         next = null;
 *     }
 * }
 */
public class Solution {
    
    public ListNode addTwoNumbers(ListNode l1, ListNode l2) {
        
        if(l1 == null && l2 == null){
        return null;
         }
    
       
    int carry = 0;
    
    return addLists(l1,l2,carry);
    }
    
    ListNode addLists(ListNode l1, ListNode l2, int carry) {
        
    if (l1 == null && l2 == null && carry == 0) {
    return null;
    }
    
    int result = 0;
    
    int value = carry;
    
    if (l1 != null) {
    value += l1.val;
    }
    
    if (l2 != null) {
    value += l2.val;
    }
    
    result = value % 10;
    
    ListNode current = new ListNode(result);
    
    current.next = addLists(l1 == null ? null : l1.next,
    l2 == null ? null : l2.next,
    value >= 10? 1 : 0);
    
        
    return current;
    }
}
