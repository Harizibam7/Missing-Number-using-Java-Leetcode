# Missing-Number-using-Java-Leetcode

    class Solution {
        public static void swap(int[] arr, int i, int correct){
            int temp = arr[i];
            arr[i] = arr[correct];
            arr[correct] = temp;
        }
        public static void sort(int[] arr){
            int i = 0;
            while(i<arr.length){
                int correct = arr[i];
                if(arr[i]<arr.length && arr[i]!=arr[correct]){
                    swap(arr,i,correct);
                }
                else{
                    i++;
                }
            }
        }
        public static int missing(int[] arr){
            for(int i = 0; i<arr.length;i++){
                if(arr[i] != i){
                    return i;
                }
            }
            return arr.length;
        }
        public int missingNumber(int[] nums) {
            Solution obj = new Solution();
            obj.sort(nums);
            int result = obj.missing(nums);
            return result;
        }
    }
