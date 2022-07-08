###question
https://leetcode.com/problems/design-twitter
###Solution
```
class Twitter {
    
    Map<Integer,Set<Tweet>> userMap;
    Map<Integer,Set<Integer>> followMap;
    
    /** Initialize your data structure here. */
    public Twitter() {
        userMap = new HashMap();
        followMap = new HashMap();
    }
    
    /** Compose a new tweet. */
    public void postTweet(int userId, int tweetId) {
        Set<Tweet> set = userMap.getOrDefault(userId, new HashSet());
        set.add(new Tweet(tweetId));
        userMap.put(userId, set);
    }
    
    /** Retrieve the 10 most recent tweet ids in the user's news feed. Each item in the news feed must be posted by users who the user followed or by the user herself. Tweets must be ordered from most recent to least recent. */
    public List<Integer> getNewsFeed(int userId) {
        
        PriorityQueue<Tweet> queue = new PriorityQueue<Tweet> ((o1,o2) ->
                                                              o1.time - o2.time);
        if(followMap.get(userId) != null) {
            for(Integer follow : followMap.get(userId)) {
                System.out.println(follow);
                if(userMap.get(follow) != null) {
                    for(Tweet tweet: userMap.get(follow)) {
                        queue.add(tweet);
                        if(queue.size() > 10) queue.poll();
                    }
                }
            }
        }
        
        if(userMap.get(userId) != null) {
            for(Tweet tweet: userMap.get(userId)) {
            queue.add(tweet);
            if(queue.size() > 10) queue.poll();
        }
        }
        
        List<Integer> list = new ArrayList();
        while(!queue.isEmpty()) list.add(0,queue.poll().tweetId);
        return list;
            
    }
    
    /** Follower follows a followee. If the operation is invalid, it should be a no-op. */
    public void follow(int followerId, int followeeId) {
        if(followerId == followeeId) return ;
        Set<Integer> set = followMap.getOrDefault(followerId,new HashSet());
        set.add(followeeId);
        followMap.put(followerId, set);
    }
    
    /** Follower unfollows a followee. If the operation is invalid, it should be a no-op. */
    public void unfollow(int followerId, int followeeId) {
        if(followerId == followeeId) return ;
        Set<Integer> set = followMap.getOrDefault(followerId,new HashSet());
        if(set.contains(followeeId)) {
            set.remove(followeeId);
        }
        followMap.put(followerId, set);
    }
}


class Tweet {
    int tweetId;
    int time;
    public static int global = 0;
    public Tweet(int tweetId) {
        this.tweetId = tweetId;
        this.time = global++;
    }
}

/**
 * Your Twitter object will be instantiated and called as such:
 * Twitter obj = new Twitter();
 * obj.postTweet(userId,tweetId);
 * List<Integer> param_2 = obj.getNewsFeed(userId);
 * obj.follow(followerId,followeeId);
 * obj.unfollow(followerId,followeeId);
 */
```

###Conclustion
Runtime beat 14%
Memory beat 39%
注意各种边界条件

###Related Topic
hash table, priorit queue,design