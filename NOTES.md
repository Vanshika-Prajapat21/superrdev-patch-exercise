# Patch Notes

## Changes Made

- Fixed the status filter in `TaskRepository.searchTasks()`. The SQL query had incorrect AND/OR precedence, causing tasks with other statuses to appear in filtered results.
- Removed the artificial `Thread.sleep()` delay from `TaskController`, which was unnecessarily slowing API responses.
- Reset pagination to page 1 when the search query or status filter changes.
- Fixed frontend error handling so failed API requests stop the loading state and display an error message.
- Added validation for invalid task status values and return a 400 Bad Request instead of a 500 error.
- Added validation for invalid pagination values such as page 0 or pageSize 0.

## Why These Fixes

I focused on user-visible and API-level issues that affected correctness, performance, and error handling. The fixes were kept small and targeted without changing the overall application architecture.

## Not Changed

I did not rewrite unrelated frontend/backend code or change the database structure because those changes were not required for the identified issues.

## Verification

I reproduced each issue locally, applied the fix, and tested the affected behavior again using the browser and API endpoints.

## Tools Used

I used VS Code, browser DevTools, local API testing, and AI(ChatGPT) assistance for debugging and understanding the existing code. All fixes were verified locally before submission.