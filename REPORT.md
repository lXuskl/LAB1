## Laboratory work I

## Tasks

## Task 1

**Скачайте библиотеку boost с помощью утилиты wget. Адрес для скачивания https://sourceforge.net/projects/boost/files/boost/1.78.0/boost_1_78_0.tar.gz**

```bash
$wget https://sourceforge.net/projects/boost/files/boost/1.78.0/boost_1_78_0.tar.gz
```
<details>

```bash
--2022-03-06 23:20:17--  https://sourceforge.net/projects/boost/files/boost/1.78.0/boost_1_78_0.tar.gz
Распознаётся sourceforge.net (sourceforge.net)... 104.18.11.128, 104.18.10.128
Подключение к sourceforge.net (sourceforge.net)|104.18.11.128|:443... соединение установлено.
HTTP-запрос отправлен. Ожидание ответа... 301 Moved Permanently
Адрес: https://sourceforge.net/projects/boost/files/boost/1.78.0/boost_1_78_0.tar.gz/ [переход]
--2022-03-06 23:20:17--  https://sourceforge.net/projects/boost/files/boost/1.78.0/boost_1_78_0.tar.gz/
Повторное использование соединения с sourceforge.net:443.
HTTP-запрос отправлен. Ожидание ответа... 301 Moved Permanently
Адрес: https://sourceforge.net/projects/boost/files/boost/1.78.0/boost_1_78_0.tar.gz/download [переход]
--2022-03-06 23:20:18--  https://sourceforge.net/projects/boost/files/boost/1.78.0/boost_1_78_0.tar.gz/download
Повторное использование соединения с sourceforge.net:443.
HTTP-запрос отправлен. Ожидание ответа... 302 Found
Адрес: https://downloads.sourceforge.net/project/boost/boost/1.78.0/boost_1_78_0.tar.gz?ts=gAAAAABiJReCmttdzrSHfsVVP-g6KllwWTr_HtNGIsSCgcO9COc4-fInxSTN8i2-L2YgGiqeIyShb-Bgt4Ho3tPn0Ki-eJ9z8g%3D%3D&use_mirror=nav&r= [переход]
--2022-03-06 23:20:19--  https://downloads.sourceforge.net/project/boost/boost/1.78.0/boost_1_78_0.tar.gz?ts=gAAAAABiJReCmttdzrSHfsVVP-g6KllwWTr_HtNGIsSCgcO9COc4-fInxSTN8i2-L2YgGiqeIyShb-Bgt4Ho3tPn0Ki-eJ9z8g%3D%3D&use_mirror=nav&r=
Распознаётся downloads.sourceforge.net (downloads.sourceforge.net)... 204.68.111.105
Подключение к downloads.sourceforge.net (downloads.sourceforge.net)|204.68.111.105|:443... соединение установлено.
HTTP-запрос отправлен. Ожидание ответа... 302 Found
Адрес: https://nav.dl.sourceforge.net/project/boost/boost/1.78.0/boost_1_78_0.tar.gz [переход]
--2022-03-06 23:20:20--  https://nav.dl.sourceforge.net/project/boost/boost/1.78.0/boost_1_78_0.tar.gz
Распознаётся nav.dl.sourceforge.net (nav.dl.sourceforge.net)... 5.154.224.27
Подключение к nav.dl.sourceforge.net (nav.dl.sourceforge.net)|5.154.224.27|:443... соединение установлено.
HTTP-запрос отправлен. Ожидание ответа... 200 OK
Длина: 131140716 (125M) [application/x-gzip]
Сохранение в каталог: ««boost_1_78_0.tar.gz»».

boost_1_78_0.tar.gz                                100%[=============================================================================================================>] 125,07M  2,56MB/s    за 1m 54s  

2022-03-06 23:22:20 (1,09 MB/s) - «boost_1_78_0.tar.gz» сохранён [131140716/131140716]

```

</details>

## Task 2

**Разархивируйте скаченный файл в директорию ~/boost_1_78_0**

```bash
$ tar -xf boost_1_72_0.tar.gz
$ rm -rf boost_1_78_0.tar.gz
```

## Task 3

**Подсчитайте количество файлов в директории ~/boost_1_78_0 не включая вложенные директории**

```bash
$ find . -maxdepth 1 -type f | wc
```

<details>

```bash
25      25     292
```

</details>

## Task 4

**Подсчитайте количество файлов в директории ~/boost_1_78_0 включая вложенные директории**

```bash
$ find . | wc
```

<details>

```bash
 95862   95866 5107933
```
</details>

## Task 5

**Подсчитайте количество заголовочных файлов, файлов с расширением .cpp, сколько остальных файлов (не заголовочных и не .cpp)**


# файлов с окончанием .hpp

```bash 
find . -type f -name *.hpp | wc -l
31095
```
# файлов с окончанием .cpp
```bash
$ find . -type f -name *.cpp | wc -l
16282
```

# файлов с окончанием ни .cpp, ни .hpp (-vc - считаем кол-во несоответствий)
```bash
$ find . -type f | grep -Evc '^.*\.(cpp|hpp)$'
40039
```

## Task 6
**Найдите полный пусть до файла any.hpp внутри библиотеки boost**

```bash
$ find `pwd` -name any.hpp
```
<details>

```bash
/home/ivan/Xusk/workspace/boost_1_78_0/boost/any.hpp
/home/ivan/Xusk/workspace/boost_1_78_0/boost/hana/any.hpp
/home/ivan/Xusk/workspace/boost_1_78_0/boost/hana/fwd/any.hpp
/home/ivan/Xusk/workspace/boost_1_78_0/boost/type_erasure/any.hpp
/home/ivan/Xusk/workspace/boost_1_78_0/boost/fusion/include/any.hpp
/home/ivan/Xusk/workspace/boost_1_78_0/boost/fusion/algorithm/query/any.hpp
/home/ivan/Xusk/workspace/boost_1_78_0/boost/fusion/algorithm/query/detail/any.hpp
/home/ivan/Xusk/workspace/boost_1_78_0/boost/proto/detail/any.hpp
/home/ivan/Xusk/workspace/boost_1_78_0/boost/spirit/home/support/algorithm/any.hpp
/home/ivan/Xusk/workspace/boost_1_78_0/boost/xpressive/detail/utility/any.hpp
/home/ivan/Xusk/workspace/boost_1_78_0/boost/geometry/geometries/adapted/detail/any.hpp
/home/ivan/Xusk/workspace/boost_1_78_0/boost_output/include/boost/any.hpp
/home/ivan/Xusk/workspace/boost_1_78_0/boost_output/include/boost/hana/any.hpp
/home/ivan/Xusk/workspace/boost_1_78_0/boost_output/include/boost/hana/fwd/any.hpp
/home/ivan/Xusk/workspace/boost_1_78_0/boost_output/include/boost/type_erasure/any.hpp
/home/ivan/Xusk/workspace/boost_1_78_0/boost_output/include/boost/fusion/include/any.hpp
/home/ivan/Xusk/workspace/boost_1_78_0/boost_output/include/boost/fusion/algorithm/query/any.hpp
/home/ivan/Xusk/workspace/boost_1_78_0/boost_output/include/boost/fusion/algorithm/query/detail/any.hpp
/home/ivan/Xusk/workspace/boost_1_78_0/boost_output/include/boost/proto/detail/any.hpp
/home/ivan/Xusk/workspace/boost_1_78_0/boost_output/include/boost/spirit/home/support/algorithm/any.hpp
/home/ivan/Xusk/workspace/boost_1_78_0/boost_output/include/boost/xpressive/detail/utility/any.hpp
/home/ivan/Xusk/workspace/boost_1_78_0/boost_output/include/boost/geometry/geometries/adapted/detail/any.hpp
```

</details>

##Task 7 

**Выведите в консоль все файлы, где упоминается последовательность boost::asio**

```bash
find . -wholename '*boost::asio*'
```
<details>

```bash

```

</details>

##Task 8 

**Скомпилирутйе boost**

```bash
$ ./bootstrap.sh --prefix=boost_output
```

<details>

```bash
Building B2 engine..

###
###
### Using 'gcc' toolset.
###
###

g++ (Ubuntu 9.3.0-17ubuntu1~20.04) 9.3.0
Copyright (C) 2019 Free Software Foundation, Inc.
This is free software; see the source for copying conditions.  There is NO
warranty; not even for MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.


###
###

> g++ -x c++ -std=c++11 -O2 -s -DNDEBUG builtins.cpp class.cpp command.cpp compile.cpp constants.cpp cwd.cpp debug.cpp debugger.cpp execcmd.cpp execnt.cpp execunix.cpp filesys.cpp filent.cpp fileunix.cpp frames.cpp function.cpp glob.cpp hash.cpp hcache.cpp hdrmacro.cpp headers.cpp jam_strings.cpp jam.cpp jamgram.cpp lists.cpp make.cpp make1.cpp md5.cpp mem.cpp modules.cpp native.cpp object.cpp option.cpp output.cpp parse.cpp pathnt.cpp pathsys.cpp pathunix.cpp regexp.cpp rules.cpp scan.cpp search.cpp startup.cpp subst.cpp sysinfo.cpp timestamp.cpp variable.cpp w32_getreg.cpp modules/order.cpp modules/path.cpp modules/property-set.cpp modules/regex.cpp modules/sequence.cpp modules/set.cpp -o b2
> cp b2 bjam
tools/build/src/engine/b2
Unicode/ICU support for Boost.Regex?... not found.
Backing up existing B2 configuration in project-config.jam.1
Generating B2 configuration in project-config.jam for gcc...

Bootstrapping is done. To build, run:

    ./b2
    
To generate header files, run:

    ./b2 headers

The configuration generated uses gcc to build by default. If that is
unintended either use the --with-toolset option or adjust configuration, by
editing 'project-config.jam'.

Further information:

   - Command line help:
     ./b2 --help
     
   - Getting started guide: 
     http://www.boost.org/more/getting_started/unix-variants.html
     
   - B2 documentation:
     http://www.boost.org/build/
```
 
</details>

```bash
$./b2 install
```
<details>

```bash
Performing configuration checks

    - default address-model    : 64-bit (cached) [1]
    - default architecture     : x86 (cached) [1]
    - compiler supports SSE2   : yes (cached) [2]
    - compiler supports SSE4.1 : yes (cached) [2]
    - has std::atomic_ref      : no  (cached) [2]
    - has statx                : yes (cached) [2]
    - has init_priority attribute : yes (cached) [2]
    - has stat::st_blksize     : yes (cached) [2]
    - has stat::st_mtim        : yes (cached) [2]
    - has stat::st_mtimensec   : no  (cached) [2]
    - has stat::st_mtimespec   : no  (cached) [2]
    - has stat::st_birthtim    : no  (cached) [2]
    - has stat::st_birthtimensec : no  (cached) [2]
    - has stat::st_birthtimespec : no  (cached) [2]
    - cxx11_auto_declarations  : yes (cached) [2]
    - cxx11_constexpr          : yes (cached) [2]
    - cxx11_defaulted_functions : yes (cached) [2]
    - cxx11_final              : yes (cached) [2]
    - cxx11_hdr_mutex          : yes (cached) [2]
    - cxx11_hdr_tuple          : yes (cached) [2]
    - cxx11_lambdas            : yes (cached) [2]
    - cxx11_noexcept           : yes (cached) [2]
    - cxx11_nullptr            : yes (cached) [2]
    - cxx11_rvalue_references  : yes (cached) [2]
    - cxx11_template_aliases   : yes (cached) [2]
    - cxx11_thread_local       : yes (cached) [2]
    - cxx11_variadic_templates : yes (cached) [2]
    - cxx11_auto_declarations  : yes (cached) [3]
    - cxx11_constexpr          : yes (cached) [3]
    - cxx11_defaulted_functions : yes (cached) [3]
    - cxx11_final              : yes (cached) [3]
    - cxx11_hdr_mutex          : yes (cached) [3]
    - cxx11_hdr_tuple          : yes (cached) [3]
    - cxx11_lambdas            : yes (cached) [3]
    - cxx11_noexcept           : yes (cached) [3]
    - cxx11_nullptr            : yes (cached) [3]
    - cxx11_rvalue_references  : yes (cached) [3]
    - cxx11_template_aliases   : yes (cached) [3]
    - cxx11_thread_local       : yes (cached) [3]
    - cxx11_variadic_templates : yes (cached) [3]
    - has_icu builds           : no  (cached) [2]
warning: Graph library does not contain MPI-based parallel components.
note: to enable them, add "using mpi ;" to your user-config.jam.
note: to suppress this message, pass "--without-graph_parallel" to bjam.
    - zlib                     : no  (cached)
    - bzip2                    : no  (cached)
    - lzma                     : no  (cached)
    - zstd                     : no  (cached)
    - has_lzma_cputhreads builds : no  (cached) [2]
    - cxx11_decltype           : yes (cached) [2]
    - cxx11_basic_alignas      : yes (cached) [2]
    - iconv (libc)             : yes (cached) [2]
    - icu                      : no  (cached) [2]
    - icu (lib64)              : no  (cached) [2]
    - native atomic int32 supported : yes (cached) [2]
    - native syslog supported  : yes (cached) [2]
    - pthread supports robust mutexes : yes (cached) [2]
    - lockfree boost::atomic_flag : yes (cached) [2]
    - compiler supports SSSE3  : yes (cached) [2]
    - compiler supports AVX2   : yes (cached) [2]
    - gcc visibility           : yes (cached) [2]
    - sfinae_expr              : yes (cached) [2]
    - cxx11_unified_initialization_syntax : yes (cached) [2]
    - cxx11_hdr_initializer_list : yes (cached) [2]
    - cxx11_hdr_chrono         : yes (cached) [2]
    - cxx11_numeric_limits     : yes (cached) [2]
    - cxx11_hdr_array          : yes (cached) [2]
    - cxx11_hdr_atomic         : yes (cached) [2]
    - cxx11_hdr_type_traits    : yes (cached) [2]
    - cxx11_allocator          : yes (cached) [2]
    - cxx11_explicit_conversion_operators : yes (cached) [2]
    - long double support      : yes (cached) [2]
warning: skipping optional Message Passing Interface (MPI) library.
note: to enable MPI support, add "using mpi ;" to user-config.jam.
note: to suppress this message, pass "--without-mpi" to bjam.
note: otherwise, you can safely ignore this message.
    - cxx11_static_assert      : yes (cached) [2]
    - std::fstream is moveable and swappable : yes (cached) [2]
    - Has Large File Support   : yes (cached) [2]
    - Has attribute init_priority : yes (cached) [2]
warning: No python installation configured and autoconfiguration
note: failed.  See http://www.boost.org/libs/python/doc/building.html
note: for configuration instructions or pass --without-python to
note: suppress this message and silently skip all Boost.Python targets
    - libbacktrace builds      : yes (cached) [2]
    - addr2line builds         : yes (cached) [2]
    - WinDbg builds            : no  (cached) [2]
    - WinDbg builds            : no  (cached) [3]
    - WinDbgCached builds      : no  (cached) [2]
    - WinDbgCached builds      : no  (cached) [3]
    - BOOST_COMP_GNUC >= 4.3.0 : yes (cached) [2]
    - BOOST_COMP_GNUC >= 4.3.0 : yes (cached) [4]
    - compiler supports SSE2   : yes (cached) [4]
    - compiler supports SSE4.1 : yes (cached) [4]
    - has std::atomic_ref      : no  (cached) [4]
    - has statx                : yes (cached) [4]
    - has init_priority attribute : yes (cached) [4]
    - has stat::st_blksize     : yes (cached) [4]
    - has stat::st_mtim        : yes (cached) [4]
    - has stat::st_mtimensec   : no  (cached) [4]
    - has stat::st_mtimespec   : no  (cached) [4]
    - has stat::st_birthtim    : no  (cached) [4]
    - has stat::st_birthtimensec : no  (cached) [4]
    - has stat::st_birthtimespec : no  (cached) [4]
    - cxx11_auto_declarations  : yes (cached) [4]
    - cxx11_constexpr          : yes (cached) [4]
    - cxx11_defaulted_functions : yes (cached) [4]
    - cxx11_final              : yes (cached) [4]
    - cxx11_hdr_mutex          : yes (cached) [4]
    - cxx11_hdr_tuple          : yes (cached) [4]
    - cxx11_lambdas            : yes (cached) [4]
    - cxx11_noexcept           : yes (cached) [4]
    - cxx11_nullptr            : yes (cached) [4]
    - cxx11_rvalue_references  : yes (cached) [4]
    - cxx11_template_aliases   : yes (cached) [4]
    - cxx11_thread_local       : yes (cached) [4]
    - cxx11_variadic_templates : yes (cached) [4]
    - cxx11_auto_declarations  : yes (cached) [5]
    - cxx11_constexpr          : yes (cached) [5]
    - cxx11_defaulted_functions : yes (cached) [5]
    - cxx11_final              : yes (cached) [5]
    - cxx11_hdr_mutex          : yes (cached) [5]
    - cxx11_hdr_tuple          : yes (cached) [5]
    - cxx11_lambdas            : yes (cached) [5]
    - cxx11_noexcept           : yes (cached) [5]
    - cxx11_nullptr            : yes (cached) [5]
    - cxx11_rvalue_references  : yes (cached) [5]
    - cxx11_template_aliases   : yes (cached) [5]
    - cxx11_thread_local       : yes (cached) [5]
    - cxx11_variadic_templates : yes (cached) [5]
    - has_icu builds           : no  (cached) [4]
    - zlib                     : no  (cached) [6]
    - bzip2                    : no  (cached) [6]
    - lzma                     : no  (cached) [6]
    - zstd                     : no  (cached) [6]
    - has_lzma_cputhreads builds : no  (cached) [4]
    - cxx11_decltype           : yes (cached) [4]
    - cxx11_basic_alignas      : yes (cached) [4]
    - iconv (libc)             : yes (cached) [4]
    - icu                      : no  (cached) [4]
    - icu (lib64)              : no  (cached) [4]
    - native atomic int32 supported : yes (cached) [4]
    - native syslog supported  : yes (cached) [4]
    - pthread supports robust mutexes : yes (cached) [4]
    - lockfree boost::atomic_flag : yes (cached) [4]
    - compiler supports SSSE3  : yes (cached) [4]
    - compiler supports AVX2   : yes (cached) [4]
    - gcc visibility           : yes (cached) [4]
    - sfinae_expr              : yes (cached) [4]
    - cxx11_unified_initialization_syntax : yes (cached) [4]
    - cxx11_hdr_initializer_list : yes (cached) [4]
    - cxx11_hdr_chrono         : yes (cached) [4]
    - cxx11_numeric_limits     : yes (cached) [4]
    - cxx11_hdr_array          : yes (cached) [4]
    - cxx11_hdr_atomic         : yes (cached) [4]
    - cxx11_hdr_type_traits    : yes (cached) [4]
    - cxx11_allocator          : yes (cached) [4]
    - cxx11_explicit_conversion_operators : yes (cached) [4]
    - long double support      : yes (cached) [4]
    - cxx11_static_assert      : yes (cached) [4]
    - std::fstream is moveable and swappable : yes (cached) [4]
    - Has Large File Support   : yes (cached) [4]
    - Has attribute init_priority : yes (cached) [4]
    - libbacktrace builds      : yes (cached) [4]
    - addr2line builds         : yes (cached) [4]
    - WinDbg builds            : no  (cached) [4]
    - WinDbg builds            : no  (cached) [5]
    - WinDbgCached builds      : no  (cached) [4]
    - WinDbgCached builds      : no  (cached) [5]

[1] gcc-9
[2] gcc-9/release/threadapi-pthread/threading-multi/visibility-hidden
[3] gcc-9/release/build-no/threadapi-pthread/threading-multi/visibility-hidden
[4] gcc-9/release/link-static/threadapi-pthread/threading-multi/visibility-hidden
[5] gcc-9/release/build-no/link-static/threadapi-pthread/threading-multi/visibility-hidden
[6] link-static

Component configuration:

    - atomic                   : building
    - chrono                   : building
    - container                : building
    - context                  : building
    - contract                 : building
    - coroutine                : building
    - date_time                : building
    - exception                : building
    - fiber                    : building
    - filesystem               : building
    - graph                    : building
    - graph_parallel           : building
    - headers                  : building
    - iostreams                : building
    - json                     : building
    - locale                   : building
    - log                      : building
    - math                     : building
    - mpi                      : building
    - nowide                   : building
    - program_options          : building
    - python                   : building
    - random                   : building
    - regex                    : building
    - serialization            : building
    - stacktrace               : building
    - system                   : building
    - test                     : building
    - thread                   : building
    - timer                    : building
    - type_erasure             : building
    - wave                     : building

...patience...
...patience...
...patience...
...patience...
...patience...
...patience...
...found 45384 targets...
```

</details>

## Task 9

**Перенесите все скомпилированные на предыдущем шаге статические библиотеки в директорию ~/boost-libs**

```bash
$ mkdir ~/boost-libs
$ cd ~boost_1_78_0/boot_output/lib 
$ mv *.* ~/boost-libs
```

## Task 10

**Подсчитайте сколько занимает дискового пространства каждый файл в этой директории**

```bash
$ du -ah
```

<details>

```bash
0	./libboost_prg_exec_monitor.so
180K	./libboost_filesystem.so.1.78.0
0	./libboost_system.so
372K	./libboost_regex.so.1.78.0
1,3M	./libboost_log.so.1.78.0
1,2M	./libboost_math_tr1f.a
0	./libboost_locale.so
48K	./libboost_timer.so.1.78.0
0	./libboost_wserialization.so
0	./libboost_log.so
0	./libboost_program_options.so
0	./libboost_context.so
0	./libboost_container.so
188K	./libboost_math_c99l.a
64K	./libboost_random.a
24K	./libboost_atomic.so.1.78.0
0	./libboost_date_time.so
0	./libboost_thread.so
280K	./libboost_contract.a
296K	./libboost_math_tr1.so.1.78.0
1,4M	./libboost_log_setup.so.1.78.0
824K	./libboost_locale.so.1.78.0
120K	./libboost_type_erasure.a
36K	./libboost_coroutine.so.1.78.0
956K	./libboost_unit_test_framework.so.1.78.0
0	./libboost_wave.so
204K	./libboost_math_c99.a
112K	./libboost_container.so.1.78.0
0	./libboost_filesystem.so
0	./libboost_math_tr1f.so
316K	./libboost_thread.a
1,2M	./libboost_serialization.a
148K	./libboost_contract.so.1.78.0
0	./libboost_timer.so
508K	./libboost_graph.so.1.78.0
76K	./libboost_math_c99.so.1.78.0
1,2M	./libboost_program_options.a
0	./libboost_iostreams.so
0	./libboost_log_setup.so
0	./libboost_math_c99f.so
24K	./libboost_nowide.a
8,0K	./libboost_context.a
0	./libboost_atomic.so
472K	./libboost_serialization.so.1.78.0
76K	./libboost_type_erasure.so.1.78.0
72K	./libboost_math_c99l.so.1.78.0
0	./libboost_math_c99.so
796K	./libboost_wserialization.a
0	./libboost_random.so
4,0K	./libboost_date_time.a
16K	./libboost_date_time.so.1.78.0
188K	./libboost_math_c99f.a
1,2M	./libboost_math_tr1.a
16K	./libboost_atomic.a
0	./libboost_chrono.so
1,2M	./libboost_math_tr1l.a
2,3M	./libboost_test_exec_monitor.a
152K	./libboost_thread.so.1.78.0
188K	./libboost_prg_exec_monitor.a
3,5M	./libboost_log.a
740K	./libboost_regex.a
488K	./libboost_json.a
284K	./libboost_math_tr1l.so.1.78.0
44K	./libboost_coroutine.a
0	./libboost_unit_test_framework.so
136K	./libboost_iostreams.a
52K	./libboost_chrono.so.1.78.0
0	./libboost_json.so
20K	./libboost_context.so.1.78.0
0	./libboost_math_tr1.so
16K	./libboost_system.so.1.78.0
32K	./libboost_nowide.so.1.78.0
72K	./libboost_math_c99f.so.1.78.0
328K	./libboost_wserialization.so.1.78.0
3,0M	./libboost_log_setup.a
0	./libboost_coroutine.so
0	./libboost_nowide.so
168K	./libboost_container.a
80K	./libboost_iostreams.so.1.78.0
0	./libboost_contract.so
0	./libboost_regex.so
2,3M	./libboost_unit_test_framework.a
524K	./libboost_program_options.so.1.78.0
480K	./libboost_filesystem.a
324K	./libboost_json.so.1.78.0
104K	./libboost_prg_exec_monitor.so.1.78.0
1,6M	./libboost_wave.so.1.78.0
0	./libboost_graph.so
48K	./libboost_random.so.1.78.0
4,0K	./libboost_exception.a
52K	./libboost_timer.a
0	./libboost_type_erasure.so
0	./libboost_serialization.so
4,0K	./libboost_system.a
276K	./libboost_math_tr1f.so.1.78.0
180K	./libboost_chrono.a
2,0M	./libboost_locale.a
0	./libboost_math_tr1l.so
1,0M	./libboost_graph.a
4,5M	./libboost_wave.a
0	./libboost_math_c99l.so
40M	.
```

</details>

## Task 11

**Найдите топ10 самых "тяжёлых"**

```bash
$ du -a | sort -n -r | head -n 10
```

<details>

```bash
40012	.
4604	./libboost_wave.a
3484	./libboost_log.a
3024	./libboost_log_setup.a
2340	./libboost_test_exec_monitor.a
2324	./libboost_unit_test_framework.a
1948	./libboost_locale.a
1540	./libboost_wave.so.1.78.0
1368	./libboost_log_setup.so.1.78.0
1236	./libboost_log.so.1.78.0
```

</details>


