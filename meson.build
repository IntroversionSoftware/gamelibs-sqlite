project('sqlite', 'c', version: '3.47.0')

compiler = meson.get_compiler('c')
c_flags = []
incdirs = ['include']

configuration = configuration_data()

if compiler.has_function('fdatasync')
    configuration.set('HAVE_FDATASYNC', 1)
endif

if compiler.has_function('gmtime_r')
    configuration.set('HAVE_GMTIME_R', 1)
endif

if compiler.has_function('isnan')
    configuration.set('HAVE_ISNAN', 1)
endif

if compiler.has_function('localtime_r')
    configuration.set('HAVE_LOCALTIME_R', 1)
endif

if compiler.has_function('localtime_s')
    configuration.set('HAVE_LOCALTIME_S', 1)
endif

if compiler.has_function('malloc_usable_size')
    configuration.set('HAVE_MALLOC_USABLE_SIZE', 1)
endif

if compiler.has_function('strchrnul')
    configuration.set('HAVE_STRCHRNUL', 1)
endif

if compiler.has_function('utime')
    configuration.set('HAVE_UTIME', 1)
endif

configItems = [
    'SQLITE_DEFAULT_AUTOMATIC_INDEX',
    'SQLITE_DEFAULT_AUTOVACUUM',
    'SQLITE_DEFAULT_CACHE_SIZE',
    'SQLITE_DEFAULT_FILE_FORMAT',
    'SQLITE_DEFAULT_FILE_PERMISSIONS',
    'SQLITE_DEFAULT_LOCKING_MODE',
    'SQLITE_DEFAULT_MEMSTATUS',
    'SQLITE_DEFAULT_PAGE_SIZE',
    'SQLITE_DEFAULT_SYNCHRONOUS',
    'SQLITE_DEFAULT_WAL_SYNCHRONOUS',
    'SQLITE_DEFAULT_WAL_AUTOCHECKPOINT',
    'SQLITE_DEFAULT_WORKER_THREADS',
    'SQLITE_DQS',
    'SQLITE_FTS3_MAX_EXPR_DEPTH',
    'SQLITE_MAX_SCHEMA_RETRY',
    'SQLITE_MEMDB_DEFAULT_MAXSIZE',
    'SQLITE_MINIMUM_FILE_DESCRIPTOR',
    'SQLITE_POWERSAFE_OVERWRITE',
    'SQLITE_PRINTF_PRECISION_LIMIT',
    'SQLITE_SORTER_PMASZ',
    'YYSTACKDEPTH',
    'SQLITE_MAX_ALLOCATION_SIZE',
    'SQLITE_OS_OTHER',
    'SQLITE_TEMP_STORE',
    'SQLITE_TRUSTED_SCHEMA',
    'SQLITE_ALLOW_COVERING_INDEX_SCAN',

    'SQLITE_DEFAULT_MMAP_SIZE',
    'SQLITE_DEFAULT_JOURNAL_SIZE_LIMIT',
    'SQLITE_DEFAULT_PCACHE_INITSZ',
    'SQLITE_MAX_MEMORY',
    'SQLITE_MAX_MMAP_SIZE',
    'SQLITE_MAX_WORKER_THREADS',
    'SQLITE_QUERY_PLANNER_LIMIT',
    'SQLITE_QUERY_PLANNER_LIMIT_INCR',
    'SQLITE_STMTJRNL_SPILL',
    'SQLITE_MAX_ATTACHED',
    'SQLITE_MAX_ATTACHED',
    'SQLITE_MAX_COLUMN',
    'SQLITE_MAX_COMPOUND_SELECT',
    'SQLITE_MAX_EXPR_DEPTH',
    'SQLITE_MAX_FUNCTION_ARG',
    'SQLITE_MAX_LENGTH',
    'SQLITE_MAX_LIKE_PATTERN_LENGTH',
    'SQLITE_MAX_PAGE_COUNT',
    'SQLITE_MAX_SQL_LENGTH',
    'SQLITE_MAX_VARIABLE_NUMBER',
    'SQLITE_THREADSAFE',
    'SQLITE_TRACE_SIZE_LIMIT',
    'SQLITE_ENABLE_8_3_NAMES'
]

foreach item : configItems
    value = get_option(item)
    if value != -1
        configuration.set(item, value)
    endif
endforeach

configFeatures = [
    'SQLITE_LIKE_DOESNT_MATCH_BLOBS',
    'SQLITE_REVERSE_UNORDERED_SELECTS',
    'SQLITE_WIN32_MALLOC',
    'SQLITE_4_BYTE_ALIGNED_MALLOC',
    'SQLITE_CASE_SENSITIVE_LIKE',
    'SQLITE_DIRECT_OVERFLOW_READ',
    'SQLITE_HAVE_ISNAN',
    'SQLITE_SECURE_DELETE',
    'SQLITE_USE_URI',
    'SQLITE_ALLOW_URI_AUTHORITY',
    'SQLITE_ENABLE_API_ARMOR',
    'SQLITE_ENABLE_ATOMIC_WRITE',
    'SQLITE_ENABLE_BATCH_ATOMIC_WRITE',
    'SQLITE_ENABLE_BYTECODE_VTAB',
    'SQLITE_ENABLE_COLUMN_METADATA',
    'SQLITE_ENABLE_DBPAGE_VTAB',
    'SQLITE_ENABLE_DBSTAT_VTAB',
    'SQLITE_ENABLE_EXPLAIN_COMMENTS',
    'SQLITE_ENABLE_FTS3',
    'SQLITE_ENABLE_FTS3_PARENTHESIS',
    'SQLITE_ENABLE_FTS3_TOKENIZER',
    'SQLITE_ENABLE_FTS4',
    'SQLITE_ENABLE_FTS5',
    'SQLITE_ENABLE_GEOPOLY',
    'SQLITE_ENABLE_HIDDEN_COLUMNS',
    'SQLITE_ENABLE_ICU',
    'SQLITE_ENABLE_IOTRACE',
    'SQLITE_ENABLE_MATH_FUNCTIONS',
    'SQLITE_ENABLE_LOCKING_STYLE',
    'SQLITE_ENABLE_MEMORY_MANAGEMENT',
    'SQLITE_ENABLE_MEMSYS3',
    'SQLITE_ENABLE_MEMSYS5',
    'SQLITE_ENABLE_NORMALIZE',
    'SQLITE_ENABLE_NULL_TRIM',
    'SQLITE_ENABLE_OFFSET_SQL_FUNC',
    'SQLITE_ENABLE_PREUPDATE_HOOK',
    'SQLITE_ENABLE_QPSG',
    'SQLITE_ENABLE_RBU',
    'SQLITE_ENABLE_RTREE',
    'SQLITE_ENABLE_SESSION',
    'SQLITE_ENABLE_SNAPSHOT',
    'SQLITE_ENABLE_SORTER_REFERENCES',
    'SQLITE_ENABLE_STMT_SCANSTATUS',
    'SQLITE_ENABLE_STMTVTAB',
    'SQLITE_ENABLE_SQLLOG',
    'SQLITE_ENABLE_STAT4',
    'SQLITE_ENABLE_UPDATE_DELETE_LIMIT',
    'SQLITE_ENABLE_UNKNOWN_SQL_FUNCTION',
    'SQLITE_ENABLE_UNLOCK_NOTIFY',
    'SQLITE_SOUNDEX',
    'SQLITE_USE_ALLOCA',
    'SQLITE_USE_FCNTL_TRACE',
    'SQLITE_USE_SEH',
    'SQLITE_HAVE_ZLIB',
    'YYTRACKMAXSTACKDEPTH',

    'SQLITE_DISABLE_LFS',
    'SQLITE_DISABLE_DIRSYNC',
    'SQLITE_DISABLE_FTS3_UNICODE',
    'SQLITE_DISABLE_FTS4_DEFERRED',
    'SQLITE_DISABLE_INTRINSIC',
    'SQLITE_DISABLE_PAGECACHE_OVERFLOW_STATS',
    'SQLITE_OMIT_ALTERTABLE',
    'SQLITE_OMIT_ANALYZE',
    'SQLITE_OMIT_ATTACH',
    'SQLITE_OMIT_AUTHORIZATION',
    'SQLITE_OMIT_AUTOINCREMENT',
    'SQLITE_OMIT_AUTOMATIC_INDEX',
    'SQLITE_OMIT_AUTORESET',
    'SQLITE_OMIT_AUTOVACUUM',
    'SQLITE_OMIT_BETWEEN_OPTIMIZATION',
    'SQLITE_OMIT_BLOB_LITERAL',
    'SQLITE_OMIT_CASE_SENSITIVE_LIKE_PRAGMA',
    'SQLITE_OMIT_CAST',
    'SQLITE_OMIT_CHECK',
    'SQLITE_OMIT_COMPILEOPTION_DIAGS',
    'SQLITE_OMIT_COMPLETE',
    'SQLITE_OMIT_COMPOUND_SELECT',
    'SQLITE_OMIT_CTE',
    'SQLITE_OMIT_DATETIME_FUNCS',
    'SQLITE_OMIT_DECLTYPE',
    'SQLITE_OMIT_DEPRECATED',
    'SQLITE_OMIT_DESERIALIZE',
    'SQLITE_OMIT_EXPLAIN',
    'SQLITE_OMIT_FLAG_PRAGMAS',
    'SQLITE_OMIT_FLOATING_POINT',
    'SQLITE_OMIT_FOREIGN_KEY',
    'SQLITE_OMIT_GENERATED_COLUMNS',
    'SQLITE_OMIT_GET_TABLE',
    'SQLITE_OMIT_HEX_INTEGER',
    'SQLITE_OMIT_INCRBLOB',
    'SQLITE_OMIT_INTEGRITY_CHECK',
    'SQLITE_OMIT_INTROSPECTION_PRAGMAS',
    'SQLITE_OMIT_JSON',
    'SQLITE_OMIT_LIKE_OPTIMIZATION',
    'SQLITE_OMIT_LOAD_EXTENSION',
    'SQLITE_OMIT_LOCALTIME',
    'SQLITE_OMIT_LOOKASIDE',
    'SQLITE_OMIT_MEMORYDB',
    'SQLITE_OMIT_OR_OPTIMIZATION',
    'SQLITE_OMIT_PAGER_PRAGMAS',
    'SQLITE_OMIT_PRAGMA',
    'SQLITE_OMIT_PROGRESS_CALLBACK',
    'SQLITE_OMIT_QUICKBALANCE',
    'SQLITE_OMIT_REINDEX',
    'SQLITE_OMIT_SCHEMA_PRAGMAS',
    'SQLITE_OMIT_SCHEMA_VERSION_PRAGMAS',
    'SQLITE_OMIT_SHARED_CACHE',
    'SQLITE_OMIT_SUBQUERY',
    'SQLITE_OMIT_TCL_VARIABLE',
    'SQLITE_OMIT_TEMPDB',
    'SQLITE_OMIT_TRACE',
    'SQLITE_OMIT_TRIGGER',
    'SQLITE_OMIT_TRUNCATE_OPTIMIZATION',
    'SQLITE_OMIT_UTF16',
    'SQLITE_OMIT_VACUUM',
    'SQLITE_OMIT_VIEW',
    'SQLITE_OMIT_VIRTUALTABLE',
    'SQLITE_OMIT_WAL',
    'SQLITE_OMIT_WINDOWFUNC',
    'SQLITE_OMIT_WSD',
    'SQLITE_OMIT_XFER_OPT',
    'SQLITE_UNTESTABLE',
    'SQLITE_ZERO_MALLOC',
    'SQLITE_DEBUG',
    'SQLITE_MEMDEBUG',
    'SQLITE_WIN32_HEAP_CREATE',
    'SQLITE_WIN32_MALLOC_VALIDATE',
]

foreach item : configFeatures
    if get_option(item).enabled()
        configuration.set(item, 1)
    endif
endforeach


if get_option('SQLITE_DEFAULT_LOOKASIDE_HIGH') != -1 and get_option('SQLITE_DEFAULT_LOOKASIDE_LOW') != -1
    result = '@0@,@1@'.format(get_option('SQLITE_DEFAULT_LOOKASIDE_HIGH'),
                            get_option('SQLITE_DEFAULT_LOOKASIDE_LOW'))
    configuration.set('SQLITE_DEFAULT_LOOKASIDE', result)
endif

configure_file(input : 'include/sqlite_cfg_meson.h.in',
               output : 'sqlite_cfg.h',
               configuration : configuration)

value = get_option('apiCall')
if value != ''
    c_flags += [
        '-DSQLITE_APICALL=' + value,
        '-DSQLITE_CALLBACK=' + value,
        '-DSQLITE_CDECL=' + value,
        '-DSQLITE_SYSAPI=' + value, 
        '-DSQLITE_TCLAPI=' + value,
    ]   
endif

incdirs = include_directories(incdirs)

c_flags += '-D_HAVE_SQLITE_CONFIG_H'

sqlite_lib = library(
    'sqlite',
    ['src/sqlite3.c'],
    c_args: c_flags,
    include_directories: incdirs,
)

sqlite_dep = declare_dependency(
    compile_args: c_flags,
    include_directories: incdirs,
    link_with: sqlite_lib,
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
