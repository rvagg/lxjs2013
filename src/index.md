
# JavaScript Databases II

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

<div style="margin-top: 0.5em; text-align: center">
  <img src="img/ogden_lxjs2013.png" style="width: 450px; border: solid white 2px; border-radius: 5px; box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.5);">
</div>

<p style="text-align: center; font-size: 12px;">**Max Ogden** - *"JavaScript Databases"* - LXJS 2012</p>

<p>"I want to see a time where I can write a persistence function that can run in Node, the browser and anywhere else JavaScript runs."</p>

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

## So what is a Database?

**A tool for interacting with structured data, externalised from the core of our application**

 * Persistence
 * Performance
 * Simplify access to complex data

Optional extras...

 * Shared access
 * Scalability

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

## The Node Way&trade;

<div class="nodeapproach">
<div data-bespoke-bullet></div>
<div data-bespoke-bullet class="second"></div>

<p class="nodedb"><b>Applied to databases?</b></p>

<p>Small core, vibrant user-land</p>
<p class="nodedb item">Small core: LevelUP</p>

<p>Extreme modularity</p>
<p class="nodedb item">Everything as a module</p>

<p>Everything in JavaScript!</p>
<p class="nodedb item">Reimplementing database *practice* &amp; *theory*</p>

</div>

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

## Inspired by LevelDB

* Open-source, embedded key/value store by Google
* Entries sorted by keys
* Basic operations: <code>Get(), Put(), Del()</code>
* Atomic <code>Batch()</code>
* Bi-directional iterators

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

## LevelDB: basic architecture

<div data-bespoke-bullet></div>

<p data-bespoke-bullet>
  <b>Log Structured Merge Tree (LSM)</b>
  <img style="float: right; width: 50%; margin: 0 -1em 0 0.5em;" src="img/leveldb_simple.svg">
</p>

<ul>
  <li data-bespoke-bullet>Writes go straight into a <b>log</b></li>
  <li data-bespoke-bullet>Log is <b>flushed</b> <i>string sorted table</i> (SST) files</li>
  <li data-bespoke-bullet>SST files grow into a hierarchy of overlapping "<b>levels</b>"</li>
  <li data-bespoke-bullet>Reads <b>merge</b> the log and the level / SST data</li>
  <li data-bespoke-bullet>Cache speeds up common reads</li>
</ul>

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

## LevelUP: Database primitives

... get, put, del, batch, readstream

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

## LevelDOWN: Storage flexibility

... leveldb forks, lmdb, level.js

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

## LevelUP: Building blocks

why batch?

readstream for queries

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

<table class="ecosystem">
  <tr class="tools">
    <td class="section"><span>Tools</span></td>
    <td><table><tr>
      <td>lev</td>
      <td>levelweb</td>
      <td></td>
      <td></td>
      <td></td>
    </tr></table></td>
  </tr>
  <tr class="packages">
    <td class="section"><span>Packages</span></td>
    <td><table><tr>
      <td>tacodb</td>
      <td>couchup</td>
      <td>LevelGraph</td>
      <td>firedup</td>
      <td>level-assoc</td>
      <td></td>
      <td></td>
      <td></td>
    </tr><tr>
      <td>level-static</td>
      <td>level-store</td>
      <td>level-session</td>
      <td>level-fs</td>
      <td>LevelTTLCache</td>
      <td></td>
      <td></td>
      <td></td>
    </tr></table></td>
  </tr>
  <tr class="extensions">
    <td class="section"><span>Extensions</span></td>
    <td><table><tr>
      <td>level-live-stream</td>
      <td>map-reduce</td>
      <td>level-queryengine</td>
      <td>Level-Multiply</td>
      <td></td>
      <td></td>
      <td></td>
    </tr><tr>
      <td>multilevel</td>
      <td>level-replicate</td>
      <td>level-master</td>
      <td>Level TTL</td>
      <td></td>
      <td></td>
      <td></td>
    </tr></table></td>
  </tr>
  <tr class="pluggability">
    <td class="section"><span>Extensibility</span></td>
    <td><table><tr>
      <td>sublevel</td>
      <td>level-hooks</td>
      <td>level-mutex</td>
      <td></td>
      <td></td>
      <td></td>
    </tr></table></td>
  </tr>
  <tr class="core">
    <td class="section"><span>Core</span></td>
    <td colspan="10">
      <table><tr><td>
        LevelUP
      </td></tr></table>
    </td>
  </tr>
  <tr class="storage">
    <td class="section"><span>Storage</span></td>
    <td colspan="10"><table><tr>
      <td class="rotate"><span><b>LevelDOWN</b></span></td>
      <td class="rotate"><span>LevelDOWN (Hyper)</span></td>
      <td class="rotate"><span>LevelDOWN (Basho)</span></td>
      <td class="rotate"><span>MemDOWN</span></td>
      <td class="rotate"><span>level.js</span></td>
      <td class="rotate"><span>leveldown-gap</span></td>
      <td class="rotate"><span>LMDB</span></td>
      <td class="rotate"><span>mysqlDOWN</span></td>
    </tr></table>
    </td>
  </tr>
</table>

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
