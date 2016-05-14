# udigest

### show unique and/or duplicate message digests

`udigest` takes the output of a message digest program
and converts the digests into small, unique digest ID numbers.

Input can come from `md5sum` or one of the `sha*sum` family.
It does not matter, as long as the input lines are in the form
of a message digest, then some white space, then the rest of the line.
Usually, the rest of the line would be a file name,
but it does not have to be, in order for `udigest` to do what it does.

The first form of output is just the digest ids and the rest,
one per line, with the actual digest stripped off.
Only the digest IDs matter.  After all, the digests themselves
can be rather long, and they are nonsense.

The second form of output is a list of triples, one per line,
consisting of:

  1. digest id
  2. count
  3. the digest itself

where _count_ is the number of input lines having that same
digest.

The third for of output is a list of only the non-unique
digests.  It consist of { id, count, digest } triples,
but only for those digest that have count >= 2,
and for each triple, all of the file names with that same
digest are listed.

### Options

`--show=`_<what>_

where _<what>_ is either 'all' or any of 'lines', 'digests', or 'dup',
or any subset of the three subset types in a comma-separated list.

`--show=lines` means just show the first form of output.
That is, just show all the lines of input, but with the digest
replaced by a digest ID.

`--show=digest` produces the second form of output.

`--show=dup` produces just the third form of output.
That is, just show the duplicates.

The default is `--show=all`,
which is equivalent to `--show=lines,digests,dup`.

--long-fmt
Print the entire input lines, message digest and all.
Normally the digests themselves are stripped,
and only the digest-ids and filenames are printed.


####

-- Guy Shaw

   gshaw@acm.org

