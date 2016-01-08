System Requirement Specification OpenFastTrack

# Introduction

## Terminology

  * Specification item: holds either a requirement or coverage
  * Specification artifact: a data source containing specification items (e.g. file, ticket system,
    database)

# Features
## Requirement Tracing
`feat~requirement_tracing~1` <a id="feat~requirement_tracing~1"/>

OFT traces requirements from specification to any kind of coverage (document, implementation, test, etc.)

Needs: req

## Requirement Import
`feat~requirement_import~1` <a id="feat~requirement_import~1"/>

OFT imports requirements from different text formats. The default is Markdown.

Needs: req

# High Level Requirements

## Coverage Status
`req~coverage_status~1` <a id="req~coverage_status~1"/>

OFT determines the coverage status of a requirement. The possible options are:

  1. Uncovered: an specification item requires coverage but is not covered
  2. Covered: a specification item requires coverage and is covered 
  3. Over covered: coverage for a specification item was found that does not exist

Covers:

  * [feat~requirement_tracing~1](#feat~requirement_tracing~1)

Needs: dsn

## Specification Item
`req~specification_item~1` <a id="req~specification_item~1"/>
A specification item consists of the following parts:

  * ID
  * Title (optional)
  * Description
  * Rationale (optional)
  * Comment (optional)
  * Covers (optional)
  * Depends (optional)
  * Needs

The ID is a unique key through which the specification item can be referenced. It also contains the specification item type and revision number.

The title is a short summary of the specification item, mostly intended to appear in overview lists.

The description contains the normative part of the specification.

The rationale explains the reasoning behind a requirement or decision.

The "Covers" section contains a list of all specification items that are covered by this item.

The "Depends" section contains a list of all specification items that must be implemented in order
for this item to be complete.

The "Needs" section list all specification item types in which coverage for this item is needed.

Needs: dsn

## Markdown Import
`req~markdown_import~1` <a id="req~markdown_import~1"/>
OFT imports specification items from Markdown.

Rationale:

Markdown is a clean an simple format that:

  * is viewable with any text editor
  * focuses on content instead of layout
  * is portable across platforms
  * easy to process with text manipulation tools
  
For those reasons Markdown is a suitable candidate for writing specification that can be read and
maintained over a long time.

Covers:

  * [feat~requirement_import~1](#feat~requirement_import~1)

Needs: dsn

### Markdown Standard syntax
`req~markdown_standard_syntax~1` <a id="req~markdown_standard_syntax~1"/>

The OFT Markdown specification artifact format uses the standard markdown syntax without proprietary extensions.

Rationale:

The specification documents that the OFT Markdown importer reads must be viewable with any regular Markdown reader and as plain text.

Covers:

  * [feat~requirement_import~1](#feat~requirement_import~1)

Needs: dsn

### Markdown Outline Readable
The Markdown outline -- an table of contents created from the heading structure by various Markdown editors -- must be human readable.

Rationale:

In long specification document the outline is the primary means of navigating the document. Only if the outline can be read easily, it is useful for authoring specification documents.

Covers:

  * [feat~requirement_import~1](#feat~requirement_import~1)

Needs: dsn 