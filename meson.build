project('sqlite', 'c', version: '3.44.2')

compiler = meson.get_compiler('c')

incdirs = include_directories(['include'])

lib = static_library(
    'sqlite',
    ['src/sqlite3.c'],
    include_directories: incdirs,
    dependencies: link_deps,
)

sqlite_dep = declare_dependency(
    include_directories: incdirs,
    dependencies: link_deps,
    link_with: lib,
    version: meson.project_version()
)

if not meson.is_subproject()
    # Build the sqlite shell if we aren't being built as a subproject
    shell = executable(
        'sqlite-shell',
        ['src/shell.c'],
        include_directories: incdirs,
        dependencies: [sqlite_dep]
    )
endif

meson.override_dependency('sqlite', sqlite_dep)

# vim: set ts=4 sts=4 sw=4 et:
