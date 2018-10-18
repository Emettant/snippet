let INVALID = 10001;
let INIT1 = -1;
let INIT2 = -2;
let dp = {};
setdp = (n,egg,ret) => {
 if (!dp[n]){
        dp[n] = {};
    }
    dp[n][egg] = ret;
}
let parent = {};
setparent = (n,egg,ret) => {
 if (!parent[n]){
        parent[n] = {};
    }
    parent[n][egg] = ret;
}
fall = (n, egg) => {
    let ret = INVALID;
    if (egg == 1 || n == 0) return n;
    if (!!dp[n] && !!dp[n][egg]) return dp[n][egg];
       
    for(let i=1;i<=n;++i)
    {
        let cand1 = fall(i-1,egg-1);
        let cand2 = fall(n-i,egg);
  let bigger = INIT1;
  let candparent = INIT2;
        if (cand2 > cand1) 
        {
   candparent = i-1;
   bigger = cand2;
  } else {
   candparent = -(n-i);
   bigger = cand1;
        }
        bigger++;
        if (ret > bigger){
   setparent(n, egg, candparent);
            ret = bigger;
        }
    }
   
    setdp(n,egg,ret);

    return ret;
};