important work

danielblakeman@Daniels-MacBook-Pro DevOps-Intro % git rev-parse HEAD
db271116511e9af65cf83a68ff818b3ce29b5e82
danielblakeman@Daniels-MacBook-Pro DevOps-Intro % git cat-file -t HEAD
commit
danielblakeman@Daniels-MacBook-Pro DevOps-Intro % git cat-file -p HEAD
tree 85cc8479d48953ad9b731f4ab11fa707fb2d8f78
parent bad2887851099644c50d12a5fb19dec748a12d4b
author Daniel Blakeman <danielblakeman15@gmail.com> 1795270885 -0500
committer Daniel Blakeman <danielblakeman15@gmail.com> 1795270885 -0500
gpgsig -----BEGIN SSH SIGNATURE-----
 U1NIU0lHAAAAAQAAADMAAAALc3NoLWVkMjU1MTkAAAAg0dd9WscULkN6sXTTZ8ZzYPJbv6
 x39nXzxWF/L6G0ec0AAAADZ2l0AAAAAAAAAAZzaGE1MTIAAABTAAAAC3NzaC1lZDI1NTE5
 AAAAQJrRh2wmmm+S+nesbm99F4e9899BQMvMZxbtNZ3Yf+un9+ihgEuFUVcQmQkNCJUpST
 U2CQ04TiA+ZA41QnnecQU=
 -----END SSH SIGNATURE-----

docs: add PR template

Signed-off-by: Daniel Blakeman <danielblakeman15@gmail.com>
danielblakeman@Daniels-MacBook-Pro DevOps-Intro % git cat-file -p bad2887851099644c50d12a5fb19dec748a12d4b
tree 879a4418251430d68ccebdcd3f1112c9d3b8ff4c
parent c42ec18bdc4433f9ce5915f55789c79fa8780858
author Dmitrii Creed <creeed22@gmail.com> 1790510974 +0400
committer Dmitrii Creed <creeed22@gmail.com> 1790510974 +0400
gpgsig -----BEGIN SSH SIGNATURE-----
 U1NIU0lHAAAAAQAAADMAAAALc3NoLWVkMjU1MTkAAAAgpI1gCp6xYZHxTcaJQoIBFt1czX
 sk7920Nox85cTfRuIAAAADZ2l0AAAAAAAAAAZzaGE1MTIAAABTAAAAC3NzaC1lZDI1NTE5
 AAAAQBx6y0D8g63uzxc0Yv1akV28VK6vSa5Vdwdk6J7HpU5HfIAhgZlmrV6S3W2KALHzML
 GmjK1a/X3otrN636vGwgk=
 -----END SSH SIGNATURE-----

docs(lab10): add GitHub Codespaces as Task 2 fallback for Render

Render asks some new accounts to verify a card, and Russian cards fail
at that step. Codespaces needs no payment method for its free quota and
every student already has a GitHub account.

Option B: a devcontainer that runs the ghcr.io image on start, a public
port 8080, and a manual stop/start cold-start measurement, since a
stopped codespace does not wake on requests. Design questions d-f get
Codespaces variants.

Signed-off-by: Dmitrii Creed <creeed22@gmail.com>
danielblakeman@Daniels-MacBook-Pro DevOps-Intro % git cat-file -p 879a4418251
100644 blob 1c0a1e94b7bbdd951f456cda51af6b8484cc3cee	.gitignore
100644 blob 4137b3baaa91461c49337bc78a99673d26d11f19	README.md
040000 tree 7d0898a908e274ea809722844cdbd836f3b1c05a	app
040000 tree 5b4aec0c1dc6cb033fa8b48348b2477ebd3f1f0b	labs
040000 tree 49b5a97bdb968d5bd602e7e06d5d188d536dcf43	lectures
danielblakeman@Daniels-MacBook-Pro DevOps-Intro % git cat-file -p 1c0a1e94b7bbdd951
# ⚠️  KEEP THIS FILE MINIMAL.
#
# This .gitignore is inherited by every student fork. Anything listed here
# is something a student CANNOT `git add` without `-f`. So this file must
# ONLY contain:
#   (a) instructor-only paths (refs/), and
#   (b) machine-generated junk that NOBODY should ever commit.
#
# Do NOT add lab DELIVERABLES here (scan reports, SBOMs, go.sum, k8s
# manifests, CI workflows, Dockerfiles, playbooks, dashboards, …). Students
# are told to commit those in their submission PRs — ignoring them upstream
# silently breaks the lab. When in doubt, leave it OUT of this file.

# ── Instructor-only ─────────────────────────────────────────────
# Reference submissions (dry-run worked examples). Never pushed upstream;
# students never see these. This is the one path that is intentionally hidden.
refs/

# ── Machine-generated junk (no one commits these) ───────────────
# Compiled binaries / local runtime state
app/quicknotes
app/data/
/quicknotes
*.exe

# Vagrant runtime state (Lab 5) — the Vagrantfile IS committed; .vagrant/ is not
.vagrant/

# Nix build symlinks (Lab 11) — flake.nix + flake.lock ARE committed; result is not
result
result-*

# Terraform state — MUST never be committed (can contain secrets)
*.tfstate
*.tfstate.backup
.terraform/

# Python virtualenvs / caches
.venv/
__pycache__/
*.pyc

# Editor / IDE
.vscode/
.idea/
*.swp

# OS noise
.DS_Store
Thumbs.db

# Local agent config (not part of the course)
.claude/

# NOTE: deliberately NOT ignored, because students commit them as lab evidence:
#   submissions/labN.md        (lab reports)
#   .github/workflows/*.yml    (Lab 3 CI)
#   Dockerfile, compose.yaml   (Lab 6)
#   ansible/                   (Lab 7)
#   monitoring/                (Lab 8)
#   *.sbom.cdx.json, zap-*.html/json, trivy-*.txt   (Lab 9 scan evidence)
#   flake.nix, flake.lock      (Lab 11)
#   wasm/main.go, spin.toml, go.sum   (Lab 12)
danielblakeman@Daniels-MacBook-Pro DevOps-Intro % ls -la .git/
total 64
drwxr-xr-x@ 15 danielblakeman  staff   480 Nov 22 01:50 .
drwxr-xr-x@  9 danielblakeman  staff   288 Nov 22 01:50 ..
-rw-r--r--@  1 danielblakeman  staff    86 Nov 22 01:27 COMMIT_EDITMSG
-rw-r--r--   1 danielblakeman  staff   539 Nov 22 01:50 config
-rw-r--r--@  1 danielblakeman  staff    73 Nov 21 08:49 description
-rw-r--r--@  1 danielblakeman  staff   371 Nov 22 01:14 FETCH_HEAD
-rw-r--r--   1 danielblakeman  staff    21 Nov 22 01:50 HEAD
drwxr-xr-x@ 16 danielblakeman  staff   512 Nov 21 08:49 hooks
-rw-r--r--   1 danielblakeman  staff  3183 Nov 22 01:50 index
drwxr-xr-x@  3 danielblakeman  staff    96 Nov 21 08:49 info
drwxr-xr-x@  4 danielblakeman  staff   128 Nov 21 08:49 logs
drwxr-xr-x@ 57 danielblakeman  staff  1824 Nov 22 01:33 objects
-rw-r--r--   1 danielblakeman  staff    41 Nov 22 01:46 ORIG_HEAD
-rw-r--r--@  1 danielblakeman  staff   112 Nov 21 08:49 packed-refs
drwxr-xr-x@  5 danielblakeman  staff   160 Nov 21 08:49 refs
danielblakeman@Daniels-MacBook-Pro DevOps-Intro % cat .git/HEAD
ref: refs/heads/main
danielblakeman@Daniels-MacBook-Pro DevOps-Intro % ls .git/refs/heads/
feature	main
danielblakeman@Daniels-MacBook-Pro DevOps-Intro % ls .git/objects/
02	0f	22	2d	40	53	5b	83	94	b8	c6	dc	ee	fc
0a	13	27	31	45	55	7a	85	9f	bb	cb	e1	f0	info
0c	1a	2a	38	4a	59	7e	8a	a3	be	cc	e4	f2	pack
0e	1d	2b	3a	4c	5a	80	8b	b7	c4	db	e8	fa
danielblakeman@Daniels-MacBook-Pro DevOps-Intro % ls .git/objects/ | head
02
0a
0c
0e
0f
13
1a
1d
22
27
danielblakeman@Daniels-MacBook-Pro DevOps-Intro % find .git/objects -type f | wc -l
'      63

