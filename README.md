
 
def merge(nums1, m, nums2, n):

    i = m - 1  # last element in the in the first part of nums1
    
    j = n - 1  # last element of nums2
    
    k = m + n - 1  #last index of nums1 which has length of m+n
    
    # to merge in reverse order 
    while i>= 0 and j>=0:
        if nums1[i]>nums2[j]:
            nums1[k]=nums1[i]
            i-=1
        else:
            nums1[k]=nums2[j]
            j-=1
        k-=1
    # if there are any remaining elements in nums2, add them to nums1
    while j>=0:
        nums1[k]=nums1[j]
        j-=1
        k-=1

nums1=[1,3,4,0,0,0]
m=3
nums2=[2,3,6]
n=3

merge(nums1,m,nums2,n)
print(nums1)  #[1,2,3,3,4,6]


# The solution merges two sorted arrays starting from the end of nums1 and nums2, comparing elements, and placing the larger element at the end of nums1.
# Time Complexity : O(m+n)
