---
title: "Files & Directories"
draft: false
---
Source: http://rubyforadmins.com/files-and-directories
{{% panel="Ruby - File" header="Ruby - File" theme="default" %}}
```ruby
File.basename('/etc/hosts')
#=> "hosts" # Equivalent to basename command

File.dirname('/etc/hosts')
#=> "etc"   # Equivalent to dirname command

File.extname('hello_world.rb')
#=> ".rb"   # Returns the file extension

File.exists?('/etc/hosts')
#=> true    # File exists?

File.file?('/etc/hosts')
#=> true    # File exists and is a file (not a directories or socket)?

File.directory?('/etc/hosts')
#=> false   # Exists and is a directory

File.readable?('/etc/hosts')
#=> true    # File exists and is a readable for the current user?

File.writable?('/etc/hosts')
#=> false   # File exists and is writable

File.executable?('/etc/hosts')
#=> false   # File exists and is executable for the current user?

File.ftype('/dev/tty')
#=> "characterSpecial" # File type

File.size('testfile')
#=> 7       # Returns file size in bytes

File.atime('/etc/passwd')
#=> 2013-10-15 13:33:56 +0200 # File last access time (returns time object)

File.mtime('/etc/passwd')
#=> 2013-10-23 10:48:46 +0200 # Modification time

File.ctime('/etc/passwd')
#=> 2013-10-23 10:48:46 +0200 # Create time

stat = File.stat('testfile')  # creates File::Stat object with status information
#=> #<File::Stat dev=0x1000004, ino=25296715, mode=0100644, nlink=1, uid=506, gid=20, rdev=0x0, size=7, blksize=4096, blocks=8, atime=2014-07-17 14:08:43 +0200, mtime=2014-07-17 14:08:43 +0200, ctime=2014-07-17 14:08:43 +0200>

stat.uid
#=> 506      # user id (integer number)

stat.gid
#=> 20       # group id

stat.mode             
#=> 33188    # file permissions - integer number

stat.mode.to_s(8)
#=> "100644" # the same permissions converted to octal number

File.rename('testfile','renamed')
#=> 0       # equivalent to mv command

File.delete('renamed')
#=> 1       # equivalent to rm command

File.realpath('.')
#=> "/Users/turbo" # returns absolute path of the given file or directory

File.realpath('/etc')
#=> "/private/etc" # and follows the symlinks
```
{{% /panel %}}

{{% panel="Ruby - Dir" header="Ruby - Dir" theme="default" %}}

The Dir class represents the directory. The same as File some of the commands are the class methods with directory name as the attribute:
```ruby
Dir.chdir('/etc')
#=> 0     # like cd command

Dir.pwd
#=> "/private/etc"  # the same as pwd command

Dir.entries('/etc')
#=> [".", "..", "aliases", "aliases.db", "apache2" ...... # returns an array of all files and dirs in a given folder

Dir.foreach('.') {|x| puts x}
# iterates on the directory contents

Dir.home
#=> "/Users/turbo" # current user home directory
```

```ruby
File.delete('foo/bar')
#=> 1   # remove directory content

Dir.rmdir('foo')
#=> 0   # and now we can delete it
```

```ruby
File.directory?('/etc')
#=> true # this is a directory

File.stat('/etc').mode.to_s(8)
#=> "40755" # directory permissions

File.ctime('/etc')
#=> 2014-07-14 15:15:17 +0200 # directory create time
```

To work with the content of the file we need to create an object instance which represents the specific file. There is the method File.open(filename, mode) for that. It takes a string with the file name and the open mode as an arguments. The mode is a way how the file will be treated:

- 'r' - means read-only open mode (default)
- 'r+' - read and write, starts at the beginning
- 'w' - write only: truncates the file to zero or creates a new if does not exists
- 'a' - append only, starts at the end of the file (or create a new one)
```
{{% /panel %}}
