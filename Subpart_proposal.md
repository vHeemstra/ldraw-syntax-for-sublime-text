## References and definitions
- For part numbering, see the [Official Library Part Number Specification](https://www.ldraw.org/part-number-spec.html)
- For file naming, see the [Official Parts Library Specifications](https://www.ldraw.org/article/512.html#filenaming)
- For part headers, see the [Official Library Header Specification](https://www.ldraw.org/article/398.html)
- `{base_part_number}` = Base part number, followed by the optional variation letter.
- `{section_number}` = Single digit (2-8) stating the section (see below)
- `{N}`, `{NN}` = incremental numbering (with possible leading zeros to match the number of `N`s

## Main part file [`Part` or `Unofficial_Part`]
- Filename: `{base_part_number}\.dat`
- Contains:
	- Stud subpart (`1` command)
	- Main subpart (`1` command)

### Main subpart file (s01) [`Subpart` or `Unofficial_Subpart`]
- Filename: `s\{base_part_number}s01.dat`
- Created in pragmatic and meaningful sections based on their orientation and/or place:
	- Top (`{section_number}` = `2`)
	- Bottom (`3`)
	- Front (`4`)
	- Bottom (`5`)
	- Left (`6`)
	- Right (`7`)
	- Other (`8`)
- Sections may contain:
	- A separate subpart for the entire section (`1` command)
	- Any reusable section subparts (`1` command)
	- Any subpart, line, triangle, quad, conditional line (like normal)
- For readibility, keep sections clean and short, or use designated section subparts
- Depending on the part and how it might be patterned in the future, some sections can be omitted.
  > For example:<br>
  > _Car doors can be divided into top, bottom, front and back sections, with the sides split into the front/back sections or included the main subpart._
  > _Half of the curved side at the hinge end would be perfect to include in the front section, since it is part of that patternable shape._
  > _The other half can be included in the back section for the same reasons._
  > _The (straight) side at the other end can be left as a quadrilateral (`4` command) in the main sub part, since it's unlikely to be patterned and doesn't need a separate subpart file._

#### Section subpart [`Subpart` or `Unofficial_Subpart`]
- Filename: `s\{base_part_number}s0{section_number}.dat`
- Contains what would otherwise be in the section in the main subpart

#### Reusable section subpart [`Subpart` or `Unofficial_Subpart`]
- Filename: `s\{base_part_number}s{section_number}{N}.dat`
- Meant for any collection of shapes that is reusable for other parts or part variations
- Usually with the dynamic part set the 1 LDu for easy scaling
- Contains any subpart, line, triangle, quad, conditional line (like normal)


## Patterned parts [`Part` or `Unofficial_Part`]
- Filename: `{base_part_number}p{NN}.dat`
- Contains:
	- Same contents as main subpart, but without the parts that are patterned
	- Patterned shapes
		- Can be any subpart, line, triangle, quad, conditional line (like normal)

## Stickered parts [`Shortcut` or `Unofficial_Shortcut`]
- Filename: `{base_part_number}d{NN}.dat`
- Contains:
	- Base part (`1` command)
	- Sticker part (`1` command)

## General notes and practices
- The above described way of sectioning a main subpart is designed to anticipate future patterning of parts, and is to prevent a complete refactoring of existing parts when a patterned version is made.<br>In this way, it's easier to take a copy of the main subpart file of the base part and just leave sections out that have to be replaced be patterned parts. In addition authors could reuse section subparts to create their patterned parts.
- Think about reusability of (section) subparts.
  - Put the origin either at the center of the subpart or at one of the ends.
  - Also have the dynamic/scalable part be 1 LDu, which makes it easier for others without having to do calculations.
- Think about where you put the outer edge lines.<br>
  - A suitable practice might be to have the lines on the XZ plane to be included in the top and bottom sections/subparts.<br>
  - All vertical outer edge lines can go in the front and back sections, leaving the sides to be (mostly) edgeless.<br>
  - Of course, this hugely depends on the shape of the part and how it might be patterned, so have a look at prior, similar parts and how they're split up.
- Studs should be left in to main part file so the main subpart file is still usable for mirrored counterparts. (Since the Lego logo on the stud should not be mirrored.)
- Don't overdo it. The objective here is to have optimal flexibility and modularity with as little overhead as possible.

