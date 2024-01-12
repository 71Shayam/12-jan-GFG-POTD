
class Solution
{
    public:
    
    // Function to reverse first k elements of a queue.
    queue<int> modifyQueue(queue<int> q, int k) {
         int n = q.size();
        
        stack<int>st;// create a stack
        for(int i=0;i<=k-1;i++){ //loop for pushing the queue element into the stack
            st.push(q.front());
            q.pop();
        }
        for(int i=0;i<k;i++){// loop for pushing back to the queue from the stack . now the Kth element is reversed
            q.push(st.top());
            st.pop();
        }
        for(int i=0;i<n-k;i++){// remaining element excluding k . pushing beck to queue
            q.push(q.front());
            q.pop();
        }
        
        return q; 
    }
};
