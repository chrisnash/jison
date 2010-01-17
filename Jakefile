#!/usr/bin/env narwhal
 
var FILE = require("file"),
    OS = require("os"),
    jake = require("jake");

jake.task("build", ["build:bnf", "build:lex"]);

jake.task("build:bnf", function () {
    OS.system(['./bin/jison', 'src/bnf.jison', 'src/bnf.jilex']);
    OS.system(['mv', 'bnf.js', 'lib/jison/util/bnf-parser.js']);
});

jake.task("build:lex", function () {
    OS.system(['./bin/jison', 'src/jilex.jison', 'src/jilex.jilex']);
    OS.system(['mv', 'jilex.js', 'lib/jison/util/lex-parser.js']);
});


jake.task("test", function () {
    OS.system(['narwhal', 'tests/all-tests.js']);
});
jake.task("test:parser", function () {
    OS.system(['narwhal', 'tests/parser/parser-tests.js']);
});
jake.task("test:lexer", function () {
    OS.system(['narwhal', 'tests/lexer/lexer-tests.js']);
});
jake.task("test:grammar", function () {
    OS.system(['narwhal', 'tests/grammar/grammar-tests.js']);
});