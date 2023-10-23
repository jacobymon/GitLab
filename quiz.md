have access to the updates we made in the test branch, and therefore the commit wouldn't reflect any changes.# Quiz questions

This is only a "quiz" in the loosest sense that it's asking questions whose

answers will be part of your grade. Please use *any resources you want*, as
long as you list those resources (e.g. peers, websites, etc.)

## Navigating logs

1. What is the SHA for the last commit made by Prof. Xanda on the branch
xanda_0000_movie_processing?
(For this and future questions, the first 5 characters is plenty - neither
Git nor I need the whole SHA.)

1 Answer: 9b257

2. What is the SHA for the last commit associated with line 9 of this file?

2 Answer: d1d83

3. What did line 12 of this file say in commit d1d83?

3 Answer: "2. I should really finish writing this."

4. What changed between commit e474c and 82045?

4 Answer: In the file process_movie_data.py, the line "gross_sort = lambda x : x["Gross"]" was changed to "gross_sort = lambda x : int(x["Gross"])" and the line "top_five = rows[:-5:-1]" was changed to "top_five = rows[:-6:-1]"

## Predicting merges

Assume at the start of each of these three questions that your
branch for switching to a top-10 list was called `top_ten`
and your branch generalizing to any number of movies was called `top_N`.
Predict the behavior of these three possible operations - you don't
have to provide a full `diff` but you should describe at a high level
what changes would happen.

These questions are supposed to be separate paths, not cumulative;
for example, you should *not* assume that the operations of 5 were run
before 6. When testing outcomes later in the lab, you should make sure to
revert back to the state of the branch before you started these questions.

5. What do you think would happen if you ran the following commands?
What branches would change, and how?
```
git checkout test
git merge top_N
```
5 Answer: I think that when we call merge, a new commit will be made from test and the last commit from top_N will now point to this commit.

6. What do you think would happen if you ran the following commands?
What branches would change, and how?
```
git checkout top_ten
git merge test
```

6 Answer: Assume you start at test, then we checkout the top_ten branch. When we merge test, there will be a new commit that the last commits from test and top_ten both point to now.

7. What do you think would happen if you ran the following commands?
What branches would change, and how?
```
git checkout test
git rebase top_ten
git rebase top_N
```

7 Answer: because rebase deletes information about the branch we were editing. when we call rebase the second time on top_N, it wouldn't have access to the updates we made in the test branch, and therefore the commit wouldn't reflect any changes.....
