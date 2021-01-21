+++
+++

# Sandboxing Editor Plugins

It seems crazy to me that, in 2021, with all the news of supply-chain-attacks and malicious packages floating around, that using an editor that _downloads and runs unsandboxed python/javascript/lua/etc_ is still ok. And that it's still a thing.

# Risks
* a major plugin is compromised
    * attackers generally seeking passwords, secrets, etc
    * targeted attacks


# Solutions
* WebAssembly + WASI
* Javascript, but with a well-defined API in a strong sandbox
* Python/lua, but with OS-level sandboxes
* Deno

# Challenges
* Possible to have all the functionality? (no)
* What to do about Language Server Protocol impls that need access to e.g. installed libraries, compilers, etc
* What about C/C++, which you can't generally even _parse_ correctly without having the headers (macros!)
* Even when sandboxed, certain classes of plugin could _edit your code_ to inject security vulnerabilities / etc

# Advantages
* Possibly enable "automatic" functionality, e.g. downloading and installing packages with little or no user involvement
