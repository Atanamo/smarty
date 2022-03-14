- revert super global access changes, and instead rely on
  USE_SUPER_GLOBALS for security

Version 2.6.25 (May 19th, 2009)
-------------------------------
- fix E_NOTICE when sessions are disabled (mohrt)

Version 2.6.24 (May 16th, 2009)
-------------------------------
- fix problem introduced with super global changes (mohrt)

Version 2.6.23 (May 13th, 2009)
-------------------------------
- strip backticks from {math} equations (mohrt)
- make PHP super globals read-only from template (mohrt)
- throw error when template exists but not readable (mohrt)

Version 2.6.22 (Dec 17th, 2008)
-------------------------------

- back out method chaining, bug in some versions of PCRE causes errors (mohrt)

Version 2.6.21 (Dec 2nd, 2008)
------------------------------

- fix  function injection security hole closed (U.Tews)
- fix pass expiration time at cache_handler_fuc call in core.write_cache_file.php (U.Tews)
- Update of compiler.class.php to allow method chaining for PHP4 and PHP5 (U.Tews)

Version 2.6.20 (Feb 15th, 2008)
-------------------------------

- fix cache tag bug when multiple cache tags on a page (mankyd,
  mohrt)
- fix /e tag checking when using arrays with regex_replace
  (mohrt)
- fix that function results can be used with condition like "is even" in 
  {if} tags (U.Tews)
- fix handling of non-empty <pre>-tags and empty <textarea>- and
  <script>-tags (Spuerhund, messju)

Version 2.6.19 (Feb 11th, 2008)
-------------------------------

- fix regex_replace allowing \0 in the search string (c960657,
  monte)
- add append feature to {capture} (jablko, monte)
- fix when (un)registering filters with the same method name but different class
  name (danilo)
- fix calling registered objects' methods with an empty argument list
  (marcello, messju)
 
Version 2.6.18 (Mar 7th, 2007)
------------------------------

- fix html_select_date separator when parts are missing (hayk,
  monte)
- fix broken detection of non-cached blocks introduced in 2.6.17
  (messju)

Version 2.6.17 (Mar 5th, 2007)
------------------------------

- fix php handling (monte, boots, danilo)
- fix handling of plugin tags directly followed by an else tag (Fahr, danilo)
- fix handling of $etc in the truncate modifier when $etc is longer
  than $length (Sylvinus, messju)
- fix handling of %I with mysql timestamps in the date_format modifier
  (danilo, boots)
- update smarty_core_write_file() and smarty_modifier_date_format() to better
  recognize Windows (boots, danilo)
- emulate %h, %n, %r, %R, %t in the date_format modifier on Windows 
  (danilo, boots)

Version 2.6.16 (Dec 1st, 2006)
------------------------------

- fixed replacement bug in trimwhitespace output filter that was introduced
  in the last release (Spuerhund, boots)

Version 2.6.15 (Nov 30th, 2006)
-------------------------------

- change file writing semantics in smarty_core_write_file() to unlink() only
  when rename() fails or a Windows system is detected (c960657, boots) 
- update debug.tpl to xhtml 1.1 compliance, fix javascript escaping in debug
  output and apply a Smarty based color scheme (cybot, boots)
- enhance reporting precision of debug_print_var modifier (cybot, boots) 
- make html_select_date work consistently with 0000-00-00 00:00:00 and
  0000-00-00 inputs (cybot, boots)
- fix wrong handling of insert's name attribute. (messju)
- fix false replacement of "$t" inside double quotes (checat, messju)
- added support for column headings and caption element to html_table and
  updated the output to use thead/tbody elements (boots)
- fixed ordering of replacements in trimwhitespace output filter (Getty, boots)
- update mailto function plugin to work around a firefox/thunderbird
  escaping bug (elijahlofgren, boots)
- emulate %l in the date_format modifier on windows (boots) 
- fix handling of apostrophes in capitalize modifier (Alec Smecher, boots)

Version 2.6.14 (May 28th, 2006)
-------------------------------

- fix compiler bug allowing php tags in secure templates
  (boots,monte)
- un-hide hidden xml open tags (boots)
- fix handling of block-methods of registered objects (El Hombre Gris,
  messju)

Version 2.6.13 (March 9th, 2006)
--------------------------------

 - update regex_replace, removing possible use of "e" modifier

Version 2.6.12 (Jan 18th, 2006)
-------------------------------

 - fix improper use of references in the compiler handling cached
   attributes and in compiled code handling block plugins (messju)
 - make Smarty::_read_file() work on latest php (messju)
 - fixed improper tokenization of certain inline math expressions (boots)

Version 2.6.11 (Dec 14, 2005)
-----------------------------

 - fixed code generation of non-cacheable blocks to play well with php's
   "Alternative syntax for control structures" (kihara, messju)
 - fix handling of multiple identical inserts in one display()-call (messju)
 - replace {} string access with equivalent substr() to avoid E_STRICT
   warnings in PHP 5.1 (boots)
 - return valid reference in get_config_vars() when given var is
   non-existant (Thomas Schulz, boots)
 - plugin html_image: fix incorrect secure_dir error when
   file doesn't exist (monte)
 - plugin html_image: add path_prefix param (monte)
 - add char_set parameter to escape modifier (Loading, monte)
 - fix notice in debug security check (Drakla, monte)
 - return valid reference in get_template_vars() when given var is
   non-existant (monte)
 - add escape type "urlpathinfo" to escape modifier (monte)

Version 2.6.10 (Aug 5, 2005)
----------------------------

  - allow secure_dir to be a filename, not just
    a directory name (monte)
  - set debug.tpl as a secure_dir, not the entire
    SMARTY_DIR (monte)
  - fix proper escaping for literal strings in
    Smarty_Compiler::_parse_var_props() (boots, messju)
  - remove ambiguity for numeric values passed to smarty_make_timestamp()
    (and thus the date_format modifier). numeric values are treated as
    timestamps now. (andreas, messju)
  - add passthru attribute feature to html_select_date (Sedgar,
    monte)
  - add "middle" parameter to truncate (monte)
  - make form input label ids optional (monte)
  - add error message for empty if/elseif statements (eykanal,
    monte)
  - cast selected value to string for comparison in html_radios
    (Exeption, monte)
  - updated html_select_date's year_as_text-feature to be xhtml compliant
    (Mark West, messju)
  - fix handling of selected month html_select_date (Yuri Weseman, messju)

Version 2.6.9 (Mar 31, 2005)
----------------------------

  - disallow variable function calls in {if} statements (messju, monte)
  - disallow variable function calls in {math} equations (messju, monte)

Version 2.6.8 (Mar 21, 2005)
----------------------------

  - remove e-modifier from regex_replace modifier (messju)
  - remove cast of object to array in foreach's from-attribute (messju)
  - add "null" as a valid token for {if} when security is enabled (messju)
  - add javascript_charcode encoding option to mailto function
    (monte)
  - add ids to html_radios labels (monte, menulis)
  - fix handling of strip-tags with non-default delimiters (Mark West, messju)

Version 2.6.7 (Feb 3, 2005)
---------------------------

  - fix handling of hashed opening php-tags inside strip-blocks (messju)
  - removed border tag from html_image function (monte)
  - change escape:url use rawurlencode() instead of urlencode() (messju)
  - make $smarty.const.FOO compile to "FOO", and not to "constant('foo')".
    this is less code and a little faster execution. note that undefined
    constants are now displayed as the constant's name. (messju)
  - make block functions and registered objects' block methods use a
    local variable for block_content instead of a property of $smarty (messju)
  - fix escaping in the generated code that calls smarty_core_load_plugins
    (jes5199, messju)
  - fix invalid HTML issue with popup (Stefanos Harhalakis,
    Monte)
  - fixed {popup} to properly handle inarray and function parameters and added
    support for mouseoff and followmouse options (boots)

Version 2.6.6 (Oct 13, 2004)
----------------------------

  - fixed nocache-handling with nested includes (Lars Jankowfsky, messju)
  - moved /libs/core to /libs/internals (boots)
  - fixed more parsing problems (messju)

Version 2.6.5 (Sept 13, 2004)
-----------------------------

  - fixed some parsing problems with object calls introduced
    in 2.6.4 (Monte)
  - add $smarty->security_settings['ALLOW_CONSTANTS']. note: this
    defaults to false which means you have to allow them explicitly
    in your secured templates from now on! (messju)

Version 2.6.4 (Sept 7, 2004)
----------------------------

  - add $smarty.ldelim and $smarty.rdelim to smarty special var (Monte)
  - fall back to old uniqid()-behaviour when tempnam() fails in
    core.write_file.php (messju)
  - fix capitalize modifier, don't rely on buggy ucwords (Monte)
  - make html_select_date work with negative timestamps, also
    force year range to include given date unless explicitly
    set (Garo, Monte)
  - fix bug with {fetch}, passing user/pass in url did not work
    (Monte)
  - fix occasional wrong error messages on mismatched tags when
    {else}, {elseif}, {foreachelse} or {sectionelse} is involved (messju)
  - fix handling of methods arguments (messju, Manfred Wischin)
  - remove touch() call that made the compiled-template's timestamp the
    same as the source-template's one. (messju)
  - add assign attribute to html_checkboxes and html_radios
    (pcg, Monte)
  - remove non-xhtml conformant tag from mailto function
    (tacker, Monte)
  - handle date_format codes %e, %T and %D for windows (tip,
    Monte)
  - fix unnecessary call to smarty_core_get_include_path() inside
    Smarty::_get_auto_filename() (c960657, messju)
  - add error-messages when anything else than an identifier is passed
    to foreach's key- or item-attribute (messju)
  - fix handling of digits inside tagnames (messju)
  - fix escaping of backslashes in Smarty_Compiler::_quote_replace() (messju)

Version 2.6.3 (June 16, 2004)
-----------------------------

  - added escapement of '</' to '<\/' in escape:javascript
    modifier (c960657, Monte)
  - added obfuscation of protocol-string in {mailto} when using hex-
    encoding (bharat, messju)
  - enhanced auto-generated filenames for templates_c and cache (messju)
  - add 'nonstd' to escape modifier for escaping non-std chars,
    such as ms doc quote (Monte)
  - adjusted textformat to not output wrap chars after last para
    (Monte)
  - use tempnam() instead of unqid() to create better temporary files in
    smarty_core_write_file() (xces, messju)
  - add 'mail' to escape modifier for safe display of e-mail
    addresses (Monte)
  - add cycle function attribute "reset" to english docs (Monte)
  - enhanced support of numeric constants as variable-expressions (messju)
  - add case decentity to smarty_modifier_escape() (Konstantin A. Pelepelin,
    messju)
  - make smarty_core_write_compiled_include() php5-aware (messju)
  - removed unused functionality to load a subset of lines from a file (messju)
  - fix is_secure() should only check if a file is_readable, not if
    the directory where it is in is readable (sagi, messju)
  - fix problem displaying debug console when $default_resource_type
    is not "file:" (c960657, Monte)
  - fix permission handling with security and config_load (messju)
  - removed '.' from the list of default template locations in
    _parse_resource_name() (messju)
  - fix avoid warning with template_exists() on an absolute paths (messju)
  - fix parameters passed to resource's secure()-function (messju)
  - fix handling of integer values like width and delay im
    smarty_function_popup() (messju)

Version 2.6.2 (Feb 17, 2004)
----------------------------

  - fix allow empty years, months and days in html_select_date's
    time-attribute (messju)
  - fix YES and NO should not be booleanized inside triple-quotes in a
    config-file (messju)
  - fix accidently slurped line following a triple-quoted value in a
    config-file (messju)
  - change default for use_sub_dirs to false (messju)
  - fix quoting of values in smarty_function_popup() (messju)
  - fix handling of hidden sections in Config_File (messju)
  - add handling of resources for {config_load} (messju)
  - fix bug when using arrays with tr_attr and td_attr in {html_table} (messju)
  - add unit testing to cvs core (Monte)

Version 2.6.1 (Jan 16, 2004)
----------------------------

  - rename $smarty->tpl_error_reporting to $smarty->error_reporting
    (messju)
  - fix interpretation of $smarty->security in {html_image} (messju)
  - add caching of requested paths to _assemble_plugin_filepath() (messju)
  - fix handling of comments inside {php}- and {literal}-blocks (messju)
  - fix bug handling triple-quotes in config-files (BRDude, messju)
  - change default of request_use_auto_globals to true - $_SERVER is
    now preferred over $HTTP_SERVER_VARS (messju)
  - re-add support for $SCRIPT_NAME (messju)
  - reactivate $smarty->default_modifiers (messju)
  - add cookie persistance to debug console (Monte)
  - allow single-digit days and months without smarty_make_timestamp()
    in html_select_date (messju)
  - fix headers sent erroneously with cache_modified_check and fetch()
    (wphilips, messju)
  - fix config_file path bug (Marc Cabadas, Monte)
  - fix 'is even by' and 'is odd by' logic (Monte)
  - add day_empty, month_empty, year_empty and all_empty attributes to
    html_select_date (messju)
  - add table of explanation for {if} qualifiers in docs (boots)
  - fix bug when comparing array-keys to "selected" in html_options
    and html_checkboxes (messju)
  - add better checks for correctly nested tags when compiling (messju)
  - remove {$SCRIPT_NAME}. use {$smarty.server.SCRIPT_NAME} instead (messju)
  - remove $global_assign. assign global variables explicitly instead (messju)
  - fix example for count_characters in docs (boots)
  - add section new basic syntax section "Escaping Smarty Parsing" in docs (boots)
  - fix error handler call in config_load (boots)
  - remove warning in debug_print_var on php-resources (messju)
  - move function.assign.php to compiler.assign.php (messju)
  - add property $tpl_error_reporting (messju)
  - remove property $undefined. "null" is used literally instead (messju)

Version 2.6.0 (Nov 19, 2003)
----------------------------

  - move Smarty::quote_replace() to Smarty_Compiler::_quote_replace() (messju)
  - remove import of of attributes of {include_php} to php's namespace.
    use $params[name] instead (messju)

Version 2.6.0-RC3 (Nov 13, 2003)
--------------------------------

  - fix handling of $var.key inside [] (messju)
  - fix handling of assign inside {insert}-tags (messju)
  - fix handling if [...] inside triple-quotes in config-files (messju)
  - fix handling of simple-math-operators inside modifiers (Dominik, messju)
  - fix handling of trailing-slashes in open_basedir in
    smarty_core_create_dir_structure() (packman, messju)

Version 2.6.0-RC2 (Oct 8, 2003)
-------------------------------

  - apply modifiers only once to section-loop and foreach-from attrs (messju)
  - remove use of _smarty_cached_paths-files (messju)
  - remove Smarty::_plugin_implementation_exists() - use is_callable() (messju)
  - ignore {strip}/{/strip) inside {strip}-blocks (messju)
  - fixed removal of leading/trailing newlines in {strip}-blocks (messju)
  - fixed proper escaping of " and ' with escape:javascript (messju)
  - fixed bug in traversal of $smarty->plugins_dir-array. now the
    first matching plugin is taken (messju)
  - moved {strip} back into the compiler (messju)
  - fixed config_load: handling of section-attribute and use of
    multiple config-files in one template (atu, messju)

Version 2.6.0-RC1 (August 11, 2003)
-----------------------------------

  - fixed status-header for cache_modified_check under cgi-sapi (messju)
  - added optional parameter $cache_attrs to register_function() and
    register_block(). $cache_attrs is an array containing attribute-
    names that should be cached on calls to functions that have
    $cacheable set to false. (messju)
  - enabled registration of class-methods as callbacks for the register_*-
    functions (use: array('classname', 'method_name')) as callback) (messju)
  - added filepath caching (Monte)
  - added optional assign-attribute to {capture}-tag (messju)
  - added $cacheable-parameter to register_compiler_function() (messju)
  - added $cacheable-parameter with default=true to register_function()
    and register_block() (messju)
  - add math speedup to core (Dominik, Monte)
  - fix newlines for tags without template output (Monte)
  - added config-option "request_use_auto_globals" to make auto-globals be
    used as request vars instead of HTTP_*_VARS (messju)
  - speed up config_load, simplify compiling (Monte)
  - added block-methods for registered objects (Bharat Mediratta, messju)
  - ignore one char resource names like c:foo.tpl (Monte)
  - added default_resource_type feature (Monte)
  - fix bug where config file starts with hidden section (boots, Monte)
  - add discrete error checking pertaining to $cache_dir
    and $compile_dir, their existance and writability (Monte)
  - fixed behaviour of start=... for {counter} (messju)
  - fixed assign for {counter} (messju)
  - added params vdir, hdir and inner to html_table to allow looping
    over the data in various directions (messju)
  - allow spaces in literal tags (Paul Lockaby, Monte)
  - speed up compiled templates, hardcode plugin filepaths
    instead of dynamically calculate at runtime. (Monte)
  - abstract many core components from Smarty.class.php,
    speeding up core class instantiation (Monte)
  - fixed bug in _create_dir_structure() when used with open_basedir-
    restriction and relative paths (messju)
  - use DIRECTORY_SEPARATOR exclusively, keep DIR_SEP for BC (Monte)
  - changed "link" to "href" in html_image. "link" is still working
    but deprecated (messju)
  - html_image always renders an alt-tag now (default alt="") (messju)
  - fixed assign attribute for multiple counters (messju)
  - added simple math operators to variables (Monte)
  - enabled array(&$obj. 'source', 'timestamp', 'secure', 'trusted')
    as callback for register_resource() (messju);
  - enabled array(&$obj, 'method') as callback for
    $default_template_handler_func (messju)
  - remove unnecessary close/open tags from compiled templates
    (Monte)
  - fixed errornous creation of '//' in image_path in html_image (messju)
  - fix escapement of special chars for key vals in debug
    console (Monte)
  - fixed debug timing logic for config_load (Tom Sommer, Monte)
  - all in-code doc comments converted to phpDocumentor format (Greg)
  - moved strip from smarty core to plugin (Monte)
  - moved config_load from smarty core to plugin (Monte)
  - added &$repeat-parameter to block-functions (messju)
  - enabled hex-constants in function.math.php (messju)
  - enabled hex-constants (0x...) as function-attributes, inside if-statements
    and as modifier-parameters (messju)
  - fixed bug with passing $smarty as reference in Smarty.compiler.class
    (messju)
  - corrected output with {strip} and PHP tag newlines (Monte)
  - added possibility to register function-callbacks as "array(&$obj, 'method)"
    this affects register_function(), -block, -compiler_function, -modifier,
    -prefilter, -postfilter, -outputfilter-functions() and $cache_handler_func
    (messju)
  - added <labels> to html_checkboxes and html_radios (Philippe, messju)
  - added "labels"-options to turn off labels in html_checkboxes and _radios
    (messju)

Version 2.5.0 (April 11, 2003)
------------------------------

   - fixed bug with default modifier when passing integer 0
     (Monte)
   - change backtic syntax from $`foo` to `$foo` (Monte)
   - recognize $foo[][] syntax inside embedded quotes without
     backtics (Monte)
   - name=123 is passed as an integer (not a string) to plugins now (messju)
   - $length is now propagated to sub-values in debug_print_var (messju)

Version 2.5.0-RC2 (March 26, 2003)
----------------------------------

    - made clear_cache() ignore compile_id, when clearing cache-groups (this
      is when no $tpl_file is supplied) (messju)
    - made onmouseout XHTML-compliant in function.popup.php (messju)
    - applied local-var-naming-scheme to fetch() (messju)
    - renamed $localvars to $_localvars in cache-file-handling-functions,
      added _get_auto_id()-function (messju)
    - swapped compile_id and cache_id in read_cache_file and write_cache_file
      (messju)
    - reverted patch for cache-file-handling (messju)
    - made html_radios and html_checkboxes accept "selected" instead
      of "checked" optionally. (messju)
    - made compile_id ignored in clear_cache, made order of
      auto_file_name $cache_id.$compile_id again, applied the the new
      variable-naming-scheme for cache_file_handing functions (messju)
    - removed notice of undefined var in _rm_auto() (messju)
    - added warning message when an array is passed as
      the "checked" value of html_radios (Monte)
    - fixed errormessage in _compile_smarty_ref() (messju)
    - updated docs for html_image "name" -> "file" (messju)
    - fixed bug with html_options-optgroups (Nichlas L�fdahl, messju)
    - cleaned up calls to readdir() (messju)
    - fixed bug with passing multiple modifiers to a parameter
      (Monte)
    - updated docs for html_checkboxes, html_options and html_radios (messju)
    - fixed wrong default "name" attribute for html_options (messju)
    - html_checkboxes now expect the options as attribute "options" instead
      of "checkboxes. html_radios expect "options" instead of "radios".
      cleaned up indentiation (messju)
    - fixed too greedy str_replace in trimwhitespace outputfilter (messju)
    - html_checkboxes and html_radios passthru all unknown paramters now
      additionally their output is now XHTML compliant (messju)
    - html_options passthru all unknown paramters now (messju)
    - fix link functionality of html_image, also make
      output XHTML compatible (Hinrich Donner, Monte)
    - append "@" to default modifier vars/args
      supress possible warnings (Monte)
    - fix problem with escaped double quotes (Monte)
    - fix html_radios to not return an array (Monte)
    - fixed length in modifier.truncate.php (messju)
    - fixed handling of '$'-signs in trimwhitespace outputfilter (messju)
    - fix bug that makes config files recompile every time
      (Nagger, Monte)
    - add dpi functionality to html_image, change "name"
      parameter to "file" (Thomas Shulz, Monte)
    - fix height/width parameter index in html_image (Gerard,
      Monte)
    - get rid of unsetting name and script attributes
      to insert tag (Thomas Schulz, Monte)
    - changed argument order of string_format modifier back,
      was right in the first place (Monte)

Version 2.5.0-RC1 (March 5, 2003)
---------------------------------

    - fixed notice in popup function (Nagger, Monte)
    - fix "once" var compiling for include_php (Monte)
    - added nl2br modifier to distribution (Monte)
    - added html_image to distribution (Monte)
    - added cat modifier to distribution (Monte)
    - added html_table to distribution (Monte)
    - added << >> <> support to if statments (SMK, Monte)
    - fix _assign_smarty_interface to not overwrite keys
      other than 'request' (Jerome Poudevigne, Monte)
    - added html_checkboxes to distribution (Christopher Kvarme, Monte)
    - added html_radios to distribution (Christopher Kvarme, Monte)
    - fixed string_format modifier args (wrong order) (Paul
      Lockaby, Monte)
    - use tmp file for file writes, avoid file lock race (Monte)
    - support syntax "$`smarty.config.foo`.tpl" for embedded
      vars in quotes, and allow full dollar var syntax (Monte)
    - add $smarty.config.varname variable for accessing config vars (Paul
      Lockaby, Monte)
    - silence PHP warnings in function.fetch.php (Eduardo,
      Monte)
    - added get_config_vars(), same basic functionality as
      get_template_vars() (Monte)
    - update get_template_vars() to be able to get
      individual vars (Monte)
    - fix minor logic in _fetch_template_info (Dennis Gearon,
      Monte)
    - fix cache groups with compile_id set (Monte)
    - add support for merging appended vars (messju, Monte)
    - allow null as function attribute value
      (Andr� Rabold, Monte)
    - support $foo->bar[index] syntax (Monte)
    - add get_registered_object function (messju, Monte)
    - treat unrecognized param attribute syntax as string (Monte)
    - support $smarty.const.$foo syntax (messju, Monte)
    - remove E_NOTICE warnings from debug.tpl,
      escape modifier (Kanstantin, Monte)
    - don't count non-ascii chars in count_words modifier
      (Kanstantin, Monte)
    - clean up param calls to _parse_var and _parse_attrs (Monte)
    - define $template_source var, elude possible warning
      (Monte)
    - fix syntax problem with evaluating PHP constants (Monte)
    - add @ and === as valid if statement tokens (Monte)
    - enable error messages for config_load errors,
      use $this->config_class for loading class name (Monte)
    - fix html_options to not escape already escaped entities (Monte)
    - send Last-Modified header on cache creation (Monte)
    - check strict syntax of function attributes (Monte)
    - dropped support for modifers on object parameters,
      added support for objects as modifier parameters (Monte)
    - fixed bug with decimal numbers in if statements (Monte)

Version 2.4.2 (Feb 11, 2003)
----------------------------
    - support embedded variables in objects (Monte)
    - fix bug with objects with no properties (M Mohr, Monte)
    - support full dollar var syntax in quoted text (Monte)
    - fixed bug in $smarty.const.FOO introduced in 2.4.1 (M
      Mohr, Monte)

Version 2.4.1 (Feb 6, 2003)
---------------------------

    - ignore case in IF statements (Rainer Collet, Monte)
    - treat undefined constants as null (Ferdinand Beyer, Monte)
    - fix problem with inserts and nested fetches
      (Rainer Collet, Monte)
    - added support for passing params to include_php
      (Tim Riley, Monte)
    - added support for math operators in if statements (Monte)
    - added support for $foo->bar[$x].blah syntax (Monte)

Version 2.4.0 (Feb 2, 2003)
---------------------------

    - fix known problems with php tag handling in templates
      (recursion, echoing xml tags) (Monte)
    - add support for object registration (Monte)
    - add debug template to secure_dir, add template_dir
      to secure_dir by default (Ferdinand Beyer, Monte)
    - added support for assigned object access (Monte)
    - fixed bug with directories named '0' (Frank Bauer, Monte)
    - add javascript parameter to escape modifier (Monte)
    - added calling function line numbers to syntax error
      messages in compiler (Monte)
    - added support for modifiers to function calls (Monte)
    - support return value for custom functions
      instead of echoing (but echo still works) (Monte)
    - added direct access to constants
      via $smarty.const.FOO (Monte)
    - added support for passing modifiers
      to static values (Monte)
    - fix up regex code in compiler, more accurate and
      maintainable (Monte)
    - added day_value_format to html_select_date (Marcus
      Bointon, Monte)
    - assigned variables are no longer in global
      namespace, saving extract() calls and speeding
      up fetch() and display() linearly with no. of
      assigned variables (Monte)
    - added trimwhitespace output filter to dist. (Monte)
    - fix popup function to allow newlines in text (Monte)
    - escape html entities in html_options (Monte)
    - fixed bug with label for html_options (Monte)
    - added config_load API function (Monte)
    - added caching to config file loading (Monte)
    - added "extra" parameter to mailto function (Monte,
      Massimiliano Perantoni)
    - added mailto plugin to dist.  (Monte)

Version 2.3.1 (Nov 19, 2002)
----------------------------

    - added optgroup support to html_options (Monte, Robert
      Amos)
    - set mtime on compile files so they match source
      files (Monte, Peter Bowen)
    - added proper support for open_basedir setting
      (Monte, Alessandro Astarita)
    - added strip variable modifier, updated docs (Monte)
    - fixed access to $smarty.x variables as arrays. (Andrei)
    - fixed errors with example setup docs (Monte, Matthew
      Hagerty)
    - added textformat block function (Monte)

Version 2.3.0 (Aug 7, 2002)
---------------------------

    - added assign_by_ref() and append_by_ref() functions
      (Bob Silva, Monte)
    - changed default warning type for plugin errors from
      E_USER_WARNING to E_USER_ERROR (Monte)
    - added $all_extra, $hour_extra, $minute_extra,
      $second_extra and $meridian_extra parameters to
      html_select_time function (Rainer Collet, Monte)
    - update debug console to print objects (Simon Willison,
      Monte)
    - fix Config_File class to not error when there are no
      sections (Peter Kmet, Monte)
    - add default modifier logic (Monte)
    - updated popup_init to be xhtml compliant (Tom Oram, Monte)
    - fix filename bug with windows (Gary Loescher, Monte)
    - add ability to supply expire time in seconds when clearing
      cache or compile files (Monte)
    - add {debug} plugin to distribution (Monte)
    - fixed bug with insert tags, loading from "script" attribute
      when caching is enabled (Monte)
    - fix bug with debug_tpl file path with Windows (.SMK., Monte)
    - fix append() function with string/array problem (Monte)

Version 2.2.0 (July 11, 2002)
-----------------------------

    - make debug.tpl work with any delimiter (Monte)
    - change logic in assign() and append() to test var names
      against != '' instead of empty() (Monte)
    - fix PHP notice in append() function (Monte)
    - allow $plugins_dir to be an array of directories
      (Andreas Kossmeier, Monte)
    - move debug.tpl to SMARTY_DIR, add to constructor (Monte)
    - fixed warning message in function.assign_debug_info (Monte)
    - fixed $template_dir, $compile_dir, $cache_dir, $config_dir,
      $plugin_dir to respect include_path (Monte)
    - fixed warning message with output filter array (Monte)
    - add optional 2nd parameter to date_format, used as
      the default date if the passed date is empty (Monte)
    - gave $reset a default value in cycle plugin (Monte)
    - fixed warnings with html_select_date and timestamp
      functions (Monte)
    - added support for sub directory exlusion format (Monte)
    - added support for grouping by cache_id, compile_id
      and segments thereof (Monte)
    - changed cache and compile files to human readable
      format (Monte)
    - remove overlib.js file from distribution (Monte)
    - fixed bug with 304 Not Modified response sending
      content (Monte)
    - fixed cycle function to respect delimiter after
      initial setting (Monte)
    - update $GLOBALS references to work properly with
      track_globals settings (Michal Prinke, Monte)
    - fixed bug in math function with call to assign
      (Grigory V. Kareev, Monte)
    - optimized for loops with count() function calls (Monte)
    - add month_value_format attribute to html_select_date
      plugin (Gary Loescher, Monte)
    - made it possible to use simple variables inside [] for
      indexing. (Andrei)
    - added "once" attribute to {include_php}. (Monte)

Version 2.1.1
-------------
    - added cycle function. (Monte)
    - fixed bug with resource testing, and include_path. (Monte)
    - fixed a bug with register_outputfilter function. (Monte)

Version 2.1.0
-------------

    - introduced output filters. (Andrei)
    - changed the way filters are loaded, added load_filter()
      API function and $autoload_filters variable. (Andrei)
    - added caching logic for expire times per cache file
      (Norbert Rocher, Monte)
    - fixed html_select_date when field separator is "/"
      (Roberto Berto, Monte)
    - added YYYY-MM-DD format support to html_select_date
      (Jan Rosier, Monte)
    - fixed cache_lifetime logic bug, also made -1 = never
      expire (Monte)
    - fixed directory separator issue for Windows. (Andrei)
    - added ability to use simple variables as array indices or
      object properties. (Andrei)
    - added ability to unregister pre/postfilters plugins at
      runtime. (Andrei)
    - added 'htmlall' attribute to escape modifier. (Monte)
    - added template_exists() API function. (Andrei)
    - fixed a problem with using dynamic values for 'file'
      attribute of {include_php} tag. (Andrei)
    - added $smarty.template variable. (Andrei)
    - fixed several plugins that would not work if the plugin
      directory was not the default one. (Andrei)
    - implemented support for block functions. (Andrei)
    - made it possible to assign variables in pre/postfilter
      plugins. (Andrei)

Version 2.0.1
-------------
    - rename plugin .make_timestamp.php to shared.make_timestamp.php.
      (Monte)
    - changed crc32() generated values, replace '-' with 'N'. (Monte)
    - added support for +/- N syntax in html_select_date year values.
      (Monte)
    - fixed behavior of inserts with script attribute. (Andrei)
    - fixed bug with $smarty.cookies and $smarty.server. (Andrei)
    - wordwrap and indent are missing from 2.0 release, now fixed.
      (Monte)
    - removed show_info_header and show_info_include variables. (Monte)

Version 2.0.0
-------------
    - added "eval" function plugin for evaluating variables as
      templates. (Monte)
    - removed $tpl_file_ext class variable, no longer used. (Monte)
    - added "hex" and "hexentity" escape types to escape modifier.
      (Monte)
    - removed dependency on PEAR. (Andrei)
    - update popup_init to accept src attribute. (Monte, Duncan Forrest)
    - implemented several optimizations, speeding up Smarty
      significantly in most cases. (Andrei,Monte)
    - implemented plugin architecture. (Andrei)
    - added wordwrap and indent modifiers. (Monte)
    - added support for 'If-Modified-Since' headers for cached content.
      (Monte)
    - removed insert_tag_check class variable, no longer needed. (Monte)
    - optimized cache fetches by scanning for insert tags only if they
      exist. (Monte)
    - fixed bugs in overlib. (Monte, Duncan Forrest)
    - fixed a problem with compile_id usage. (Andrei)
    - fixed problem with using assigned vars with {include_php ...}
      filepath. (Monte)

Version 1.5.2
-------------
    - added Smarty object as fifth argument for template resource functions.
      (Monte)
    - fixed a bug with incorrectly combined cache and compile id in
      clear_cache(). (Andrei)
    - fixed bug in smarty_make_timestamp introduced in PHP 4.1.0. (Monte)
    - fixed bug with cached insert debug timing. (Monte)
    - added 'script' attribute to {insert..} which specifies the script that
      the insert function can be found in. (Andrei)
    - added default template function handler. (Monte)

Version 1.5.1
-------------
    - removed error message from the generic _read_file() method, the caller
      should take care of that. (Andrei)
    - fixed a bug with incorrectly combined cache and compile id. (Andrei)

Version 1.5.0
-------------
    - added include_php built-in function, documented. (Monte)
    - added trusted_dir functionality, documented. (Monte)
    - consolidated secure_dir tests to one function. (Monte)
    - prepended _smarty_ to variable names in fetch() class function to avoid
      namespace conflicts. (Monte)
    - introduced $compile_id class variable that can be used to set persistent
      compile identifier across multiple display calls, documented. (Andrei)
    - fixed bug with concatenated null cache and compile identifiers. (Andrei)
    - added $smarty.section.* syntax for accessing section properties,
      documented. (Andrei)
    - added custom cache handling function ability, documented. (Monte)
    - added assign attribute to include, include_php, insert, fetch, math, and
      counter functions, documented. (Monte)
    - fixed bug with fetch testing for local file when http address. (Monte)
    - fixed bug with counter and skipval setting. (Monte)
    - made {config_load ...} merge globals from each config file only once per
      scope, thus avoiding several problems. (Andrei)
    - added {foreach ...} tag that can be used to iterate through
      non-sequential and associative arrays, documented. (Andrei)
    - speeded up section property access a bit. (Andrei)
    - removed $smarty variable from storage used by normal template variables,
      to prevent any problems. (Andrei)
    - fixed a bug that could cause parse error with quotes inside literal
      blocks. (Andrei, Alexander Belonosov)
    - added 'field_array' attribute to html_select_time function, documented.
      (Andrei, Michael Caplan)
    - documented {section} "max" attribute. (Monte)
    - fixed notice message in Smarty_Compiler.class.php. (Monte)
    - fixed bug with clear_cache introduced in 1.4.6, third parameter should
      default to null. (Monte)
    - updated Config_File class to support '\' path separator in OS/2. (Monte,
      Francesco Cipriani)
    - removed secure_ext setting (not used). (Monte)
    - made cache reading process more efficient. (Monte)
    - fixed bug, is_cached() now supports new 1.4.6 caching behavior. (Monte)
    - update FAQ with mailing list Reply-To header FAQ. (Monte)
    - supress error messages for fopen(), fix cache to regenerate if cache
      file is not available (i.e. cluster race condition). (Monte)
    - added index key example to QUICKSTART guide. (Monte)

Version 1.4.6
-------------
    - fixed bug with {assign ...} when passing an empty value. (Monte)
    - add more warning message fixes. (Monte, Tara Johnson)
    - documentation updates. (Monte)
    - update fetch function to give proper warning when fetching a non-readable
      or non-existant file. (Monte)
    - fixed problem with newline at the end of included templates (Monte, Andrei)
    - added feature to regenerate cache if compile_check is enabled and an
      involved template or config file gets modified. (Monte)
    - added DEBUG execution times to included files: REQUIRES updated debug.tpl
      file! (Monte)
    - added support for hidden config variables that cannot be read by
      templates. (Andrei)
    - added execution time to DEBUG console, total and inserts. (Monte)
    - fixed bug where DEBUG console would not appear with cached content. (Monte)
    - added support for postfilter functions that are applied to compiled
      template right after compilation. (Andrei)
    - fixed the name of clear_compile_tpl() API function to clear_compiled_tpl.
      (Andrei)
    - added fix for removing comments so that the line numbers are reported
      correctly in case of errors. (patch from Anders Janson)
    - made html_options output xhtml compatible code. (Monte, Arnaud Limbourg)

Version 1.4.5
-------------
    - update FAQ with index of questions at the top
    - update overlib to 3.50, adjust addon code so that the overlib.js
      file isn't modified, and not using the mini one. (Monte)
    - added many more options to html_select_date. (Alexander Skwar, Andrei)
    - added support for generating different compiled templates from the same
      source template. (Hans-Peter Oeri, Andrei)
    - modified Smarty to pass itself to insert functions as the second
      parameter. (Andrei)
    - modified Smarty to pass itself to prefilter functions as the second
      parameter. (Andrei)
    - fixed syntax error when including a non-existant template with security
      enabled. (Monte)
    - fixed comments handling to allow commenting out template blocks. (Andrei)
    - implemented named capture buffers, with results accessible via
      $smarty.capture.<name>. (Andrei)
    - added ability to index arrays directly by numbers. (Andrei)
    - fixed bug with SMARTY_DIR not prepended to Config_File include. (Monte)

Version 1.4.4
-------------
    - fixed problem with including insecure templates with security enabled.
      (Monte)
    - numerous documentation updates. (Monte)
    - added ENT_QUOTES to escapement of html. (Monte, Sam Beckwith)
    - implemented access to request variables via auto-assigned $smarty
      template variable. (Andrei)
    - fixed a bug with parsing function arguments inside {if} tags if a comma
      was present. (Andrei)
    - updated debug console with config file vars. (Monte)
    - added SMARTY_DIR constant as an alternative to relying on include_path.
      (Monte)
    - added popup_init and popup functions (requires overlib.js). (Monte)
    - updated debug console with config file vars. (Monte)
    - added debugging url control. (Monte)
    - added 'quotes' type to escape modifier. (Monte, Mike Krus)
    - added 'total' and 'iteration' section properties. (Andrei)
    - added 'start', 'max', and 'step' section attributes/properties. (Andrei)
    - fixed a bug with security checking of functions inside {if} tags.
      (Andrei)
    - fixed a bug in Config_File that would incorrectly booleanize values that
      weren't really booleans. (Andrei)

Version 1.4.3
-------------
    - added regex_replace modifier, documented. (Monte)
    - added debugging console feature and custom function assign_debug_info,
      documented. (Monte)
    - added 'scope' attribute for {config_load}, 'global' is now deprecated but
      is still supported. (Andrei)
    - reduced template symbol table pollution by moving config array into the
      class itself. (Andrei)
    - fixed a bug with passing quoted arguments to modifiers inside {if}
      statements. (Andrei, Sam Beckwith)
    - added security features for third party template editing, documented
      (Monte)
    - added assign custom function, documented. (Monte)
    - fixed bug with template header using version instead of _version. (Monte)
    - fixed a problem with putting $ followed by numbers inside {strip} and
      {/strip} tags. (Andrei)
    - fixed Config_File class to allow empty config paths (defaults to current
      directory). (Andrei)

Version 1.4.2
-------------
    - move $version to internal variable, remove from docs. (Monte)
    - cleaned up compiled templates global scope by moving some variables into
      the class itself. (Andrei)
    - fixed a bug that would not allow referring to a section in the including
      file from the included file. (Andrei)
    - configs directory missing from 1.4.1 release, added back in. (Monte)
    - added windows include_path setup instructions to FAQ & QUICKSTART.
      (Monte)

Version 1.4.1
-------------
    - fix LOCK_EX logic for all windows platforms (Monte)
    - fixed indexing by section properties with the new syntax. (Andrei)
    - updated Smarty to use absolute paths when requiring/including Smarty
      components. (Andrei, John Lim)

Version 1.4.0
-------------
    - added {capture}{/capture} function, documented (Monte)
    - added {counter} function, documented (Monte)

Version 1.4.0b2
---------------
    - fixed issue in Config_File.class with referencing blank sections (Andrei)
    - fixed problem with passing variables to included files (Andrei)
    - fixed resource path recognition for windows (Monte)

Version 1.4.0b1
---------------
    - added "componentized templates" tip into documentation (Monte)
    - added {php}{/php} tags for embedding php code into templates (Monte)
    - changed default value of $show_info_header to false (Monte)
    - implemented '->' syntax for accessing properties of objects passed to the
      template. (Andrei)
    - allowed custom functions to receive Smarty object as the second
      parameter; this can be used to dynamically change template variables, for
      example. (Andrei)
    - added custom compiler functions support, register_compiler_function() and
      unregister_compiler_function() API functions. (Andrei, Ivo Jansch).
    - updated GLOBAL_ASSIGN to take SCRIPT_NAME from HTTP_SERVER_VARS
      instead of global variable. You can also assign several variables
      in one shot with an array. (Monte, Roman Neuhauser)
    - added template prefilters, register_prefilter() and
      unregister_prefilter() API functions. (Monte)
    - added RELEASE_NOTES file to distribution. (Monte)
    - moved CREDITS out of manual into its own file. (Monte)
    - added register_resource() and unregister_resource() API functions. (Monte)
    - changed the syntax of indexing template variables, thus supporting
      structures of arbitrary complexity; supplied fix_vars.php script to fix
      old syntax. (Andrei)
    - added $insert_tag_check to speed up cached pages if {insert ...} is not
      used. (Monte)
    - added $compiler_class variable to allow specifying a different compiler
      class. (Andrei)
    - changed Smarty to compile templates at runtime, allowing for arbitrary
      template resources. (Monte)
    - added fix for LOCK_EX under Windows and changed a couple of file
      permissions for security. (Monte, Fernando Nunes)
    - allow arbitrary date strings to date_format, html_select_date and
      html_select_time (Monte)

Version 1.3.2
-------------
    - fixed a bug that caused some nested includes to loop infinitely. (Andrei)
    - added optional HTML header to output. (Monte)
    - significantly improved config_load performance. (Andrei)
    - added format attribute to math function. (Monte)
    - added html_select_time custom function. (Andrei)
    - fixed minor PHP warning when attempting to unset an unset variable
      (Monte)
    - added count_characters, count_words, count_sentences, count_paragraphs
      modifiers (Monte)

Version 1.3.1pl1
--------------
    - bug fix, recovered missing _syntax_error function (Monte)

Version 1.3.1
-------------
    - document first, last, index_prev, index_next (Monte)
    - added 'first' and 'last' section properties. (Andrei)
    - split out compiling code to separate class for faster template execution
      time (Monte)
    - fixed a couple of minor PHP warnings (Monte)
    - added and documented unregister_modifier() and unregister_function() API
      calls. (Monte)
    - added and documented 'fetch' and 'math' functions. (Monte)
    - added ability to index looped variables by section properties, e.g.
      $foo.index_prev/bar. (Andrei)
    - added index_prev and index_next section properties. (Andrei)
    - fixed issue with php executing in literal blocks. (Monte)

Version 1.3.0
-------------
    - moved license from GPL to LGPL (Monte)
    - implemented workaround for PHP "feature" that eats carriage returns
      if the PHP tag is at the end of the line. (Andrei)
    - removed $allow_php, added $php_handling logic (Monte)
    - added file locking to prevent reader/writer problem. (Andrei)
    - made Smarty catch unimplemented modifiers and custom functions and output
      error messages during compilation instead of failing during run time.
      (Andrei)
    - removed short-tags at the top of the smarty scripts (Monte)
    - added register_function() and register_modifier() API calls to make
      registering stuff easier. (Andrei)
    - added template results caching capability. (Monte, Andrei)
    - added optional 'options' attribute to html_options custom function
      that allows passing associative arrays for values/output. (Andrei)
    - modifier arguments can now contain '|' and ':' characters inside quoted
      strings. (Andrei)

Version 1.2.2
-------------
    - fixed bug that would not respect nested template directories and would
      put all compiled files into top-level one. (Andrei)
    - fixed bug using $PHP_VERSION instead of environment var PHP_VERSION.
      (Monte)
    - a couple small warning fixes. (Monte)

Version 1.2.1
-------------
    - added $compile_dir, removed $compile_dir_ext, simplified usage. (Monte)
    - added tips & tricks chapter to documentation. (Monte)
    - misc documentation updates. (Monte)

Version 1.2.0
-------------
    - updated documentation (Monte)
    - added file and line number information to syntax error messages. (Andrei)
    - added ability to index template vars by a key. (Andrei)

Version 1.1.0
-------------
    - misc documentation changes, official stable release

Version 1.0b
------------
    - fixed the bug that prevented using non-array values for 'loop' attribute.
      (Andrei)
    - many misc documentation changes & additions (Monte)

Version 1.0a
------------
    - fixed bug that caused templates to recompile every time (Monte)

Version 1.0
------------
    - initial release

/* vim: set et tw=64 ft=changelog: */