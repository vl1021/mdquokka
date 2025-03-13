 +:---------------:+:---------------------:+:--------------------:+:----------------------:+:----------------------:+
 | Datapost Header |  Public Data Manifest |  Public Data Consent |  Private Data Manifest |  Private Data Content  |
 +-----------------+-----------------------+----------------------+------------------------+------------------------+

 ----------------- ---------------------- --------------------- ----------------------- ----------------------
  Datapost Header   Public Data Manifest   Public Data Consent   Private Data Manifest   Private Data Content  
 ----------------- ---------------------- --------------------- ----------------------- ---------------------- 

 ----------- ------- --------------- -------------------------
   First    row                12.0 Example of a row that
                                    spans multiple lines.

  Second    row                 5.0 Here's another one. Note
                                    the blank line between
                                    rows.
----------- ------- --------------- -------------------------

Alignments can be specified as with pipe tables, by putting colons at the boundaries of the separator line after the header:

+---------------+---------------+--------------------+
| Right         | Left          | Centered           |
+==============:+:==============+:==================:+
| Bananas       | $1.34         | built-in wrapper   |
+---------------+---------------+--------------------+
For headerless tables, the colons go on the top line instead:

+--------------:+:--------------+:------------------:+
| Right         | Left          | Centered           |
+---------------+---------------+--------------------+
A table foot can be defined by enclosing it with separator lines that use = instead of -:

 +---------------+---------------+
 | Fruit         | Price         |
 +===============+===============+
 | Bananas       | $1.34         |
 +---------------+---------------+
 | Oranges       | $2.10         |
 +===============+===============+
 | Sum           | $3.44         |
 +===============+===============+
