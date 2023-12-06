# Hey! I'm Filing Here

In this lab, I successfully implemented the following functions.

<ul>
    <li>write_superblock</li>
    <li>write_block_group_descriptor_table</li>
    <li>write_block_bitmap</li>
    <li>write_inode_bitmap</li>
    <li>write_inode_table</li>
    <li>write_root_dir_block</li>
    <li>write_hello_world_file_block</li>
</ul>

These functions in addition to the given skeleton code created a 1MiB ext2 file system with 2 directories, 1 regular file, and 1 symbolic link.

## Building

To build this program, run the command
```shell
make
```

## Running

To create the image of the filesystem (cs111-base.img), run the program
```shell
./ext2-create
```

The specificiations of the Ext2 file system can be checked with the following commands:

```shell
dumpe2fs cs111-base.img
```
which will output information about the filesystem

```shell
fsck.ext2 cs111-base.img
```
which will pass through the file system 5 times checking for different errors, and 

```shell
mkdir mnt
sudo mount -o loop cs111-base.img mnt
ls -ain mnt
```
which will call ls with the options -ain on the mounted filesystem mnt to show the directories and files in our filesystem.

## Cleaning up
To remove the executables generated from calling make, run
```shell
make clean
```

If the last test in the Running section was called, use the following to unmount and remove the mounted filesystem.
```shell
sudo umount mnt
rmdir mnt
```
