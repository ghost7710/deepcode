# 88

```c
void merge(int* nums1, int nums1Size, int m, int* nums2, int nums2Size, int n){
for(int i=0;i<n;i++){
    nums1[m+i]=nums2[i];
}
for(int j=0;j<m+n-1;j++){
    for(int k=0;k<m+n-1;k++){
        if(nums1[k]>nums1[k+1]){
            int temp=nums1[k];
            nums1[k]=nums1[k+1];
            nums1[k+1]=temp;
        }
    }
}
}
```

# 234

将链表值传入数组

```c
/**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     struct ListNode *next;
 * };
 */


bool isPalindrome(struct ListNode* head){
    int cnt=pow(10,5);
int vals[cnt], n = 0;
    while (head != NULL) {
        vals[n] = head->val;
        n++;
        head = head->next;
    }
    for (int i = 0, j = n- 1; i < j; ++i, --j) {
        if (vals[i] != vals[j]) {
            return false;
        }
    }
    return true;
}
    
```

# 349

```c
/**
 * Note: The returned array must be malloced, assume caller calls free().
 */
void SelectSort(int *nums,int numsSize){
   int min,temp;
   for(int i=0;i<numsSize-1;i++){
        min=i;
        for(int j=i+1;j<numsSize;j++){
            if(nums[min]>nums[j]){
                min=j;
            }
        }
        if(min!=i){
            temp=nums[min];
            nums[min]=nums[i];
            nums[i]=temp;
        }
    } 
}

int* intersection(int* nums1, int nums1Size, int* nums2, int nums2Size, int* returnSize) {
    int temp,i,j;
    int *result=(int *)malloc(nums2Size*sizeof(int));

    //选择排序
    SelectSort(nums1,nums1Size);
    SelectSort(nums2,nums2Size);

    *returnSize=0;
    temp=nums1[nums1Size-1]+1;  //给temp赋一个不可能与nums1或nums2冲突的值
    for(i=0,j=0;i<nums1Size&&j<nums2Size;){
        if(nums1[i]>nums2[j]){
            j++;
        }
        else if(nums1[i]<nums2[j]){
            i++;
        }
        else{
            if(temp!=nums1[i]){
                result[(*returnSize)++]=nums1[i];
                temp=nums1[i];
            }
            i++;
            j++;

        }
    }
    return result;
}

```

