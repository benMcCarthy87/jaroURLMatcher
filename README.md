# jaroURLMatcher

When a websites structure is changed, URLs need to be 301 redirected. Commonly this is an oversight of a site re-launch and commonly URLs need to be manually matched. This algorythem uses the  [Jaro–Winkler distance](https://en.wikipedia.org/wiki/Jaro%E2%80%93Winkler_distance) to find the nearest match between new and old URLs. Because of the time complexity of checking every potential match (exponentially increasing for large migrations), after the first 10 matches, any match with a Jaro–Winkler similarity higher than the mean, will match without searching the rest of the list, this will also remove the URL from the 'new_URL' list to reduce time complexity. This can be overwritten by changing the variables to False in the header of the code. 

This will only work where the URL structure has changed, moving from a structure of unclear URLs (example.com/qrte6473/0000123a to example.com/hats/green-hats/)
