- Feature Name: Content View Version Comparison
- Start Date: 9/22
- RFC PR: (leave this empty)
- Issue: (leave this empty)

# Summary
[summary]: #summary
This feature will allow a user to compare content in two different content view versions. 

# Motivation
[motivation]: #motivation
This allows users to debug issues between content view versions by comparing two content view versions.
One example of this is - I have promoted a CVV to a different Lifecycle Environment and I am now experiencing
issues. What packages are different in the CVV that was pushed up versus the CVV that was originally there?

# Detailed design
[design]: #detailed-design

In mockups/ is a design document with mock ups of the UI design

In this design, the user goes to the content view details > versions tab. They select two different versions to compare and click 'compare'. This then brings them to the compare page.

Here there are tabs for each type of content. The user can select the tab they want and the table will display with the comparison of those two content view versions. The list is searchable, and also can be filtered by repository. The user can also sort the list by content view version or alphabetically. 

3 different options can be shown
- Diff: Show the packages that are only in one CVV
- Same: Show the packages that are in both CVVs
- All: Show all packages in one or both CVVs

The user can then pick another content view version to compare up above, and can even compare across content views.

The Compare page should be modular, as in the future we look to compare other items like lifecycle environments, repositories, etc... This first iteration will just be for comparing content view versions. Another idea is to show a page like this when you are publishing a content view. Adding a compare page like this will open up a lot of possibilities for Katello.

# Drawbacks
[drawbacks]: #drawbacks
I honestly can't think of any drawbacks to adding this feature.

# Alternatives
[alternatives]: #alternatives

One alternative is we just do this from the CLI.

# Unresolved questions
[unresolved]: #unresolved-questions
One outstanding question is whether we should have a way to navigate to the compare page from a more top-level menu? 

Since there is only CVV compare in this first iteration, maybe we can add a "compare versions" button at the header of the content view page (next to 'create new content view') that will bring them to the compare page where they select CVVs to compare. This would allow users to directly compare versions across content views.

The initial version of this will just allow two different content view versions to be compared. In the future, we are considering comparing multiple content view versions, and that will require updating the dropdown content view/content view version selectors that you can see in the Compare page.

IMHO, Diff, Same, All are the most clear way to describe the type of view they are seeing. Most users should be comfortable with what 'diff' means, while 'same' and 'all' are self-explanatory. That being said, other suggestions are welcome for these names.
