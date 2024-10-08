- 👋 Hi, I’m @nacy-ezlove
- 👀 I’m live in Vietnam 🇻🇳
- 🌱 My favorite game is valorant
- 💞️ I'm secretly in love with...💓
- 📫 How to reach me ...
- 😄 Pronouns: xàm lồn
- ⚡ Fun fact: gay=))
<!---
nacy-ezlove/nacy-ezlove is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
nblocks = nblocks ? : 1;

	group_info = kmalloc(sizeof(*group_info) + nblocks*sizeof(gid_t *), GFP_USER);

	if (!group_info)

		return NULL;

	group_info->ngroups = gidsetsize;

	group_info->nblocks = nblocks;

	atomic_set(&group_info->usage, 1);



	if (gidsetsize <= NGROUPS_SMALL)

		group_info->blocks[0] = group_info->small_block;

	else {

		for (i = 0; i < nblocks; i++) {

			gid_t *b;

			b = (void *)__get_free_page(GFP_USER);

			if (!b)

				goto out_undo_partial_alloc;

			group_info->blocks[i] = b;

		}

	}

	return group_info;



out_undo_partial_alloc:

	while (--i >= 0) {

		free_page((unsigned long)group_info->blocks[i]);

	}

	kfree(group_info);
