```mermaid
graph TD;
A[Initial Page Load] -->|Fetch HTML, JS (spa.js), CSS| B[Server];
B -->|Respond with files| C[Browser];
C -->|Execute spa.js| D[Fetch Notes as JSON];
D -->|Render Notes with DOM| E[User Sees Notes];

E -->|User Enters Note| F[Form Input];
F -->|Click Add Note| G[JavaScript Interception];
G -->|Prevent Default Submission| H[Create New Note Object];
H -->|Add to Local Array| I[Render Note Locally];
I -->|Display Note| J[User Sees New Note];

G -->|Send Note to Server| K[HTTP POST to /new_note_spa];
K -->|Send JSON Data| L[Server];
L -->|Parse JSON, Add Note to Array| M[Respond 201 Created];

M -->|No Redirect| N[Stay on Same Page];
N -->|Smooth User Experience| J;
```
