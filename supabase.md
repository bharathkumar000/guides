# ⚡ Supabase: The Instant Backend for Modern Applications

Setting up databases, writing authentication APIs, and configuring security headers can take days or weeks of manual engineering. **Supabase** simplifies this by instantly giving you a full, production-ready PostgreSQL database, user sign-in APIs, and real-time database listener connections out of the box.

Think of it as Firebase, but built on standard SQL rather than a custom NoSQL structure.

---

## 🗺️ How Row-Level Security (RLS) Protects Your Data

In standard backends, you write API middleware to check if a user is allowed to access a database record. In Supabase, the database itself checks this directly via **Row-Level Security (RLS)**. 

Here is how a request is evaluated under RLS:

```mermaid
flowchart TD
    User["👤 User Request\n'Select * from diaries where id = 5'"] --> AuthCheck{"🔑 Is User Logged In?"}
    AuthCheck -->|No| Reject["❌ Access Denied\n401 Unauthorized"]
    AuthCheck -->|Yes| RLS{"🛡️ RLS Policy Engine\nDoes user.id == diary.user_id?"}
    RLS -->|No (Trying to read rival's diary)| Reject
    RLS -->|Yes| Approve["✅ Query Executed\nRecords returned safely"]

    style Reject fill:#d63031,stroke:#c0392b,color:#fff
    style Approve fill:#00b894,stroke:#00a884,color:#fff
```

---

## 🚀 Setting Up Your First Table

Let's build a secure backend for a **Secret Diary App** (so your teammates can't spy on your notes).

### Step 1: Create the Table in Supabase
In the Supabase SQL Editor, run the following SQL command to create your table:
```sql
create table diaries (
  id bigint generated always as identity primary key,
  user_id uuid references auth.users not null default auth.uid(),
  title text not null,
  content text not null,
  created_at timestamp with time zone default timezone('utc'::text, now()) not null
);
```

### Step 2: Enable Row-Level Security (RLS)
Turn on the security vault for this table:
```sql
alter table diaries enable row level security;
```

### Step 3: Create the Access Policy
Create a policy that allows logged-in users to read and write **only their own** diaries:
```sql
create policy "Users can only read their own diaries"
  on diaries for select
  using ( auth.uid() = user_id );

create policy "Users can only insert their own diaries"
  on diaries for insert
  with check ( auth.uid() = user_id );
```

---

## 💻 Querying Database in Frontend (JavaScript)

```javascript
import { createClient } from '@supabase/supabase-js'

const supabase = createClient('https://your-url.supabase.co', 'your-public-anon-key')

// Insert a new diary entry securely
async function saveDiary(title, content) {
    const { data, error } = await supabase
        .from('diaries')
        .insert([{ title, content }]);
        
    if (error) console.error("Error writing to database:", error.message);
    else console.log("Diary saved safely under user's account!", data);
}
```

---

## 🕹️ Backend Integration Dashboard

Ready to wire your database to other parts of your workspace? Click these navigation buttons:

<div align="center" style="margin: 20px 0;">
  <a href="file:///Users/bharathkumara/Desktop/guides/api%20keys.md" style="text-decoration:none;">
    <button style="background-color:#6c5ce7; color:white; border:none; padding:10px 18px; font-size:14px; border-radius:6px; cursor:pointer; font-weight:bold; margin:5px; box-shadow: 0 2px 4px rgba(0,0,0,0.1);">
      🔑 Secure Database Keys
    </button>
  </a>
  <a href="file:///Users/bharathkumara/Desktop/guides/vercel.md" style="text-decoration:none;">
    <button style="background-color:#0984e3; color:white; border:none; padding:10px 18px; font-size:14px; border-radius:6px; cursor:pointer; font-weight:bold; margin:5px; box-shadow: 0 2px 4px rgba(0,0,0,0.1);">
      ☁️ Deploy Backend Config
    </button>
  </a>
</div>
