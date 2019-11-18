project('osxfuse', version: '3.10.3')
run_command('./build.sh', '-t', 'library')
run_command('cp', '-r', '/tmp/osxfuse/distribution/Core/usr/local/', './build')

# Add dependency
cplr = meson.get_compiler('cpp')
projectDir  = meson.current_source_dir()
incdir = include_directories('./build/include/osxfuse')

osxfuse = cplr.find_library('osxfuse', dirs: projectDir + '/build/lib')

libfuse_dep = declare_dependency(include_directories: incdir,
  dependencies: [osxfuse])