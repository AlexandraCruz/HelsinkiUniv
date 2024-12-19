graph TD

A[Initial Page Load] -->|Fetch HTML, JS, CSS| B[Server]
B -->|Respond with files| C[Browser]
C -->|Execute spa.js| D[Fetch Notes as JSON]
D -->|Render Notes with DOM| E[User Sees Notes]

subgraph User Interaction
    E -->|Enter Note| F[Form Input]
    F -->|Click Add Note| G[JavaScript Intercepts]
    G -->|Prevent Default Submission| H[Create New Note Object]
    H -->|Add to Local Array| I[Render Note Locally]
    I -->|Display Note| J[User Sees New Note]
end

G -->|Send Note to Server| K[HTTP POST to /new_note_spa]
K -->|Send JSON Data| L[Server]
L -->|Add Note to Server-Side Array| M[Respond 201 Created]

M -->|No Redirect| N[Stay on Same Page]
N -->|Enhance UX| J
