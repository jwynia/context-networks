# Document Archiving Process

This document outlines the process for archiving documents after they have been integrated into the context network.

## Overview

The archiving process ensures that original documents are preserved for reference while keeping the inbox folder clear for new incoming documents. This maintains a clean workflow while preserving the original context of information.

## Process Steps

1. **Pre-Archiving Verification**
   - Confirm that all relevant information has been extracted from the document
   - Verify that new nodes have been created and properly linked in the context network
   - Ensure that any updates to existing nodes have been completed

2. **Archive Location Setup**
   - If it doesn't already exist, create an `archive/` folder at the same level as the `inbox/` folder
   - Organize the archive folder with appropriate subfolders if needed (e.g., by date, category, or source)

3. **Document Preparation**
   - Add a header to the document indicating it has been processed:
     ```
     ---
     Status: Archived
     Processed Date: [Date]
     Integrated Into: [List of nodes created/updated]
     ---
     ```
   - This header helps track the document's processing history if it needs to be referenced later

4. **Document Transfer**
   - Move the document from the `inbox/` folder to the appropriate location in the `archive/` folder
   - Maintain the original filename to ensure traceability
   - If multiple documents have the same name, append a date or version number

5. **Archive Index Update**
   - If maintaining an archive index, update it with:
     - Document name
     - Original location
     - Archive date
     - Brief description
     - Nodes created/updated from this document

6. **Inbox Cleanup**
   - Verify that the document has been successfully moved to the archive
   - Ensure the inbox folder is empty and ready for new documents

## Special Considerations

### Document Versions

If a document is an updated version of a previously archived document:
- Archive it as a new document with a version indicator
- Note in the header that it supersedes a previous version
- Update any affected nodes with the new information

### Referenced Documents

If a document is frequently referenced:
- Consider creating a "frequently referenced" section in the archive
- Add additional cross-references in relevant nodes

### Large Documents

For very large documents:
- Consider creating a summary document that highlights key points
- Archive both the original and the summary
- Reference the summary in the context network nodes

## Maintenance

Periodically review the archive to:
- Ensure documents remain accessible
- Verify that the organization structure remains effective
- Consider if any archived documents contain information that should be integrated into the context network

## Archive Recovery

If information from an archived document needs to be revisited:
1. Locate the document in the archive
2. Review the processing header to identify related nodes
3. If necessary, extract additional information and update the context network
4. Update the processing header to reflect the additional extraction
