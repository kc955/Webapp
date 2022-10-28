<script>
	import * as fs from 'fs';
    import path from 'path';
	var dir = 'webapp/src/routes/resource/posters';
	let err;
	let files;
	dir = path.resolve(dir);
	fs.readdir(dir, (err, files) => {
		if (err) {
			throw err
		}
		console.log(files)
	});
</script>



