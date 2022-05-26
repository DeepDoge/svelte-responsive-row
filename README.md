# What's this?

-   A svelte component for creating a responsive row.

# How does it work?

-   You pick an `ideal size` for the columns or items.
-   (Optionally) You can pick a `gap size`. (**default:** `.1em`)
-   And, it determines the column count on every row based on the ideal and gap size.
-   Then it sets the column size as `row width / column count`.
-   And, when there is only `1` column per row it shrinks the column if it doesn't fit. (for mobile and stuff)
