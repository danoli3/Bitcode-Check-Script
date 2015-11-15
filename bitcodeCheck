#!/bin/bash
#
# The MIT License (MIT)

# Copyright (c) 2015 Daniel Rosser <danoli3@gmail.com>

# Permission is hereby granted, free of charge, to any person obtaining a copy
# of this software and associated documentation files (the "Software"), to deal
# in the Software without restriction, including without limitation the rights
# to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
# copies of the Software, and to permit persons to whom the Software is
# furnished to do so, subject to the following conditions:

# The above copyright notice and this permission notice shall be included in all
# copies or substantial portions of the Software.

# THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
# IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
# FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
# AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
# LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
# OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
# SOFTWARE.
here="`dirname \"$0\"`"
echo "cd-ing to $here"
cd "$here" || exit 1

echo "==================================================="
echo "---- bitcodeCheck - Bitcode Check Script v1.0 ----"

# bitcodeCheck
# Param1: archive to check for bitcode
# Param2: any string to slow the checking down
bitcodeCheck(){

if [ "$1" == "" ]
then
    echo "----------------------"
    echo "ERROR! Missing Parameter 1 - 'archive location"
    echo "   example: bitcodeCheck \"boost_system.a\""
    echo "----------------------"
    exit;
fi

echo "------------------"
if [ ! -f $1 ]; then
    echo "ERROR! File does not exist: $1"
else
    LLVM=`otool -l $1 | grep __LLVM`
    #echo $LLVM
    if [ -z "$LLVM" ]; then
        echo "BITCODE=NO for: $1"
    else
        echo "BITCODE=YES for: $1"
    fi
fi

# 
if [ "$2" != "" ]; then
    sleep 1 
fi

}


bitcodeCheckHere() {
    local TOBECHECKED
    for TOBECHECKED in $( ls *.a) ; do
        bitcodeCheck $TOBECHECKED
    done
}



# --------------- Example if you want to add files to check here:

# bitcodeCheck "openFrameworks/libs/boost/lib/tvos/boost_system.a"

# or just call the follow to check all archives in a directory
# bitcodeCheckHere 

echo "==================================================="

#===============================================================================
