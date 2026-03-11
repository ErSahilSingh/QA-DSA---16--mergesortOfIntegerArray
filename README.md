# QA-DSA---16--mergesortOfIntegerArray

var merge = function(nums1, m, nums2, n) {
    let nums1copy= nums1.slice(0,m)
    let p1=0;
    let p2=0;
    for(let i=0; i<m+n ; i++){
        if(p2>=n||(p1<=m && nums1copy[p1]<nums2[p2])){
            nums1[i]=nums1copy[p1]
            p1++
        }else{
             nums1[i]=nums2[p2]
            p2++
        }
    }
    return nums1
    
};


///
function mergetwosort(nums1, nums2) {
    let nums3 = []
    let i = 0;
    let j = 0;
    while (i<nums1.length && j<nums2.length) {
        if (nums1[i]<nums2[j]) {
            nums3.push(nums1[i])
            i++
        } else {
            nums3.push(nums2[j])
            j++
        }
    }
    return [...nums3,...nums1.slice(i),...nums2.slice(j)]
}

console.log(mergetwosort([1, 3, 5, 6], [4, 6, 8, 9]))
