for stale cache protection we will try to fetch and update the render process cache frequently with a standard background process. 
this will be a persistent process
generate a list of dirs in node backend and then in render cache
merge the diffs
and take node dir list as source of truth.
