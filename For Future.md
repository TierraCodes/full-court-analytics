## Bugs/Issues
* Email provider may have trouble if you try to use anything other than gmail.
* Markdown in email does not format correctly. Shows # text instead of bold "**text**". It correctly formats within the sight but on gmail itself does not.

## Improvements
* Tasks only store in the database but do not trigger cloud run/scheduler.
* Google API refresh tokens only work for local machine and are not production ready yet.
* Site was never tested with large amounts of data. May need optimization later down the road.
