# Exercises 12 - Random

## Goal
```
Output:Please pass me a seed (integer).
Input:1234
Output:Three integers between 0 and 5:
Output:1
Output:4
Output:1
Output:Three numbers between 0.0 and 0.5:
Output:0.47336876693804225
Output:0.16971801229273809
Output:0.47438912045880643
Output:Three numbers between 0.2 and 0.7:
Output:0.6039959450736623
Output:0.46036547346057627
Output:0.5219790320480144
Output:Give me a crit chance between 0,0 (0%) and 1,0 (100%)
Input:0,7
Output:Crit
Output:Crit
Output:No Crit
Output:No Crit
Output:Crit
```

## Instructions
- Create a Console Project named `P12Random` [How To?](https://gist\.github\.com/marczaku/a8b3c38c37e8876a46194a73ed24b1f2)
- Ask the User for a Seed and store it in a variable.
- Initialize Random with the given Seed.
- Get three Random Numbers between 0 and 5 (including 0, excluding 5) and print them to the Console.
- Get three Random Numbers between 0 and 0.5 (including 0, excluding 0.5) and print them to the Console.
- Get three Random Numbers between 0.2 and 0.7 (including 0.2, excluding 0.7) and print them to the Console.
- Ask the user for a Crit Chance between 0.0 (0%) and 1.0 (100%). 
  - Then simulate 5 Attacks and write, whether it’s a Crit. Or No Crit. 
- Hint: Thanks to using the Seed, you should actually receive the same results as me below, if using the same Seed. Test it! :)