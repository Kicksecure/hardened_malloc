# security-focused general purpose memory allocator #

This is a security-focused general purpose memory allocator providing the
malloc API along with various extensions. It provides substantial hardening
against heap corruption vulnerabilities. The security-focused design also
leads to much less metadata overhead and memory waste from fragmentation than
a more traditional allocator design. It aims to provide decent overall
performance with a focus on long-term performance and memory usage rather than
allocator micro-benchmarks. It offers scalability via a configurable number of
entirely independently arenas, with the internal locking within arenas further
divided up per size class.

It can be added as a preloaded library using /etc/ld.so.preload.

Ships two files:

* [1]
/usr/lib/x86_64-linux-gnu/libhardened_malloc.so/libhardened_malloc.so
* [2]
/usr/lib/x86_64-linux-gnu/libhardened_malloc.so/libhardened_malloc-light.so

[1] Was compiled with Hardened Malloc Default compilation parameters.

[2] Was compiled with Hardened Malloc Light compilation parameters.

## How to install `hardened_malloc` using apt-get ##

1\. Download the APT Signing Key.

```
wget https://www.kicksecure.com/keys/derivative.asc
```

Users can [check the Signing Key](https://www.kicksecure.com/wiki/Signing_Key) for better security.

2\. Add the APT Signing Key.

```
sudo cp ~/derivative.asc /usr/share/keyrings/derivative.asc
```

3\. Add the derivative repository.

```
echo "deb [signed-by=/usr/share/keyrings/derivative.asc] https://deb.kicksecure.com bookworm main contrib non-free" | sudo tee /etc/apt/sources.list.d/derivative.list
```

4\. Update your package lists.

```
sudo apt-get update
```

5\. Install `hardened_malloc`.

```
sudo apt-get install hardened_malloc
```

## How to Build deb Package from Source Code ##

Can be build using standard Debian package build tools such as:

```
dpkg-buildpackage -b
```

See instructions.

NOTE: Replace `generic-package` with the actual name of this package `hardened_malloc`.

* **A)** [easy](https://www.kicksecure.com/wiki/Dev/Build_Documentation/generic-package/easy), _OR_
* **B)** [including verifying software signatures](https://www.kicksecure.com/wiki/Dev/Build_Documentation/generic-package)

## Contact ##

* [Free Forum Support](https://forums.kicksecure.com)
* [Premium Support](https://www.kicksecure.com/wiki/Premium_Support)

## Donate ##

`hardened_malloc` requires [donations](https://www.kicksecure.com/wiki/Donate) to stay alive!
