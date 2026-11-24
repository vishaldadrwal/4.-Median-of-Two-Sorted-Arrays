# 4. Median of Two Sorted Arrays
# Given two sorted arrays nums1 and nums2 of size m and n respectively, return the median of the two sorted arrays.  
# The overall run time complexity should be O(log (m+n)).

class Solution {
public:
    double findMedianSortedArrays(vector<int>& nums1, vector<int>& nums2) {
        int m = nums1.size();
        int n = nums2.size();
        vector<int> arr;
        // Copy elements of first array
        for(int i = 0; i < m; i++) {
            arr.push_back(nums1[i]);
        }
        // Copy elements of second array
        for(int i = 0; i < n; i++) {
            arr.push_back(nums2[i]);
        }
        // Sort the combined array
        sort(arr.begin(), arr.end());
        int total = m + n;
        int mid = total / 2;
        // Odd number of elements
        if(total % 2 != 0) {
            return arr[mid];
        }
        // Even number of elements
        else {
            return (arr[mid - 1] + arr[mid]) / 2.0;
        }
    }
};

