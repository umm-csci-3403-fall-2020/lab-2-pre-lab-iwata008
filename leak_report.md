# Leak report

I found the memory leak in the is_clean function which was cleaned variabe.

cleaned was causing the memory leak because it was used in return = strcmp(str,cleaned) when it was supposed to be freed, but was never freed.

free method would break when cleaned was empty so I used free(cleaned) in the if statement to check if cleaned was NOT empty. 
