#
# Licensed to the Apache Software Foundation (ASF) under one
# or more contributor license agreements. See the NOTICE file
# distributed with this work for additional information
# regarding copyright ownership. The ASF licenses this file
# to you under the Apache License, Version 2.0 (the
# "License"); you may not use this file except in compliance
# with the License. You may obtain a copy of the License at
#
#   http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing,
# software distributed under the License is distributed on an
# "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY
# KIND, either express or implied. See the License for the
# specific language governing permissions and limitations
# under the License.
#
#
# Contains some contributions under the Thrift Software License.
# Please see doc/old-thrift-license.txt in the Thrift distribution for
# details.

AM_YFLAGS = -d 
LIBS =
BUILT_SOURCES =

SUBDIRS = . py

bin_PROGRAMS = thrift1

noinst_LTLIBRARIES = libparse.la libthriftcompilerbase.la

libthriftcompilerbase_la_SOURCES = common.cc \
				   parse/t_type.cc \
			           parse/t_typedef.cc

libthriftcompilerbase_la_LDFLAGS = -lcrypto


thrift1_OBJDIR = obj

thrift1_SOURCES = main.cc \
                 generate/t_generator.cc \
                 globals.h \
                 main.h \
                 platform.h \
                 parse/t_doc.h \
                 parse/t_type.h \
                 parse/t_base_type.h \
                 parse/t_enum.h \
                 parse/t_enum_value.h \
                 parse/t_typedef.h \
                 parse/t_container.h \
                 parse/t_list.h \
                 parse/t_set.h \
                 parse/t_map.h \
                 parse/t_stream.h \
                 parse/t_struct.h \
                 parse/t_field.h \
                 parse/t_service.h \
                 parse/t_function.h \
                 parse/t_program.h \
                 parse/t_scope.h \
                 parse/t_const.h \
                 parse/t_const_value.h \
                 generate/t_generator.h \
                 generate/t_oop_generator.h \
                 generate/t_html_generator.h 

# Specific client generator source
thrift1_SOURCES += generate/t_cpp_generator.cc \
                  generate/t_java_generator.cc \
                  generate/t_csharp_generator.cc \
                  generate/t_py_generator.cc \
                  generate/t_rb_generator.cc \
                  generate/t_perl_generator.cc \
                  generate/t_php_generator.cc \
                  generate/t_hack_generator.cc \
                  generate/t_erl_generator.cc \
                  generate/t_cocoa_generator.cc \
                  generate/t_st_generator.cc \
                  generate/t_ocaml_generator.cc \
                  generate/t_hs_generator.cc \
                  generate/t_xsd_generator.cc \
                  generate/t_html_generator.cc \
                  generate/t_js_generator.cc 

thrift1_LDFLAGS = -lfolly -lcrypto -lglog
thrift1_LDADD = @LEXLIB@ libparse.la libthriftcompilerbase.la

libparse_la_CPPFLAGS = $(AM_CPPFLAGS) -DTHRIFTY_HH=\"thrift/compiler/thrifty.hh\"
libparse_la_SOURCES = thrifty.yy \
                     thriftl.ll

clean-local:
	$(RM) thriftl.cc thrifty.cc thrifty.h version.h 

main.cc: version.h
