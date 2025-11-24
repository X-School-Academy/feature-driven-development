<feature-driven-development-rules>  
When you start to work, please say: "I am your feature-driven code developer", so I know you have read and understand these rules.

If I say `task xxx`, check the task in the file `prompts/xxx.md`, then follow these rules:

1. Refine the task and write it to `features/yyy-zzz.md` for review. Once the user confirms, proceed with the implementation.
2. After finishing the code, write the documentation and APIs to `features/docs/yyy-zzz.md` and `features/apis/yyy-zzz.md` for review. Once the user confirms, the implementation is considered complete.
3. The `yyy-zzz` name should be short and self-descriptive as a design feature, so it should not contain words such as issue, add, update, bugfix, refactor, ticket, etc.
4. The documentation is for reference by other developers, so it should include file paths, function names, and other relevant keywords for quick code search and review (do not use line No. as a reference).
5. The APIs file defines interfaces for internal or external development — it should follow standard API documentation conventions or be usable as a package/module reference.
6. If the task is large or consists of multiple parts, split it into subtasks, then follow rule #1 and complete each subtask one by one, with user confirmation after each.

If I say `complete yyy zzz`, it means to check the file `features/yyy-zzz.md`, and complete the implementation, create `features/docs/yyy-zzz.md` and `features/apis/yyy-zzz.md` as needed.
If I say `refer yyy zzz`, it means to refer to `features/yyy-zzz.md`, and read `features/docs/yyy-zzz.md` or `features/apis/yyy-zzz.md` if needed.
If I say `review yyy zzz`, it means to perform a code review for `features/yyy-zzz.md` using `features/docs/yyy-zzz.md` and `features/apis/yyy-zzz.md` to understand the current implementation.
If I say `refer to` or `update` the design spec, that means the `*.md` files in the `features` folder.
If I say `search xxx`, that means you need to search the internet to get the solution.

You can update `features/docs/yyy-zzz.md` and `features/apis/yyy-zzz.md` during a code review after making fixes or updates, once the user confirms. However, do not update `features/yyy-zzz.md` unless the user explicitly asks you to.

For any bug fix or task update, you must update the related `features/yyy-zzz.md`, `features/docs/yyy-zzz.md`, and `features/apis/yyy-zzz.md` promptly to keep them synchronized with the current code and implementation.

Therefore, for any `task`, we may not need to create a new feature — instead, we might update an existing one.
In general, always ask the user to confirm before creating or updating any files under the `features` folder.

Do not include test cases etc. in files `features/**/*.md` unless asked, as test cases are not a feature.
In `features/**/*.md`, do not refer to other files that are not part of the source code, or not under the `features` folder. If I mentioned some references in `prompts/xxx.md`, please extract and write the related content to `features/docs/yyy-zzz.md` or `features/yyy-zzz.md` for docs.

Maintain a file named `features/readme.md` that includes all the `*.md` files directly under the `features` folder, along with other general information about this project.
Keep the content of `features/readme.md` as concise as possible while still providing enough information to help preserve your memory.

Periodically read and update `features/readme.md` in your memory so you can better understand any `refer` or `review` command and maintain full context of the project. 

All the file paths mentioned are relative to the project root.

If I say `do`, check the currently opened markdown file in vs code; it may mean to do a `task` or a `complete` based on which folder the file is in.
</feature-driven-development-rules>