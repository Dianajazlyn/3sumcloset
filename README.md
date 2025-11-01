# 3sumcloset
Arrays.sort(nums);
        int n = nums.length;
        int closestSum = nums[0] + nums[1] + nums[2]; // Initialize with first 3 sum

        for (int i = 0; i < n - 2; i++) {
            int left = i + 1, right = n - 1;

            while (left < right) {
                int sum = nums[i] + nums[left] + nums[right];

                // Update closest if this sum is closer to target
                if (Math.abs(target - sum) < Math.abs(target - closestSum)) {
                    closestSum = sum;
                }

                if (sum < target) {
                    left++;  // Need a larger sum
                } else if (sum > target) {
                    right--; // Need a smaller sum
                } else {
                    return sum; // Exact match found
                }
            }
        }

        return closestSum;
   
