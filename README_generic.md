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
## How to install `hardened_malloc` using apt-get ##

1\. Add [Whonix's Signing Key](https://www.whonix.org/wiki/Whonix_Signing_Key).

```
sudo apt-key --keyring /etc/apt/trusted.gpg.d/whonix.gpg adv --keyserver hkp://ipv4.pool.sks-keyservers.net:80 --recv-keys 916B8D99C38EAF5E8ADC7A2A8D66066A2EEACCDA
```

3\. Add Whonix's APT repository.

```
echo "deb http://deb.whonix.org buster main contrib non-free" | sudo tee /etc/apt/sources.list.d/whonix.list
```

4\. Update your package lists.

```
sudo apt-get update
```

5\. Install `hardened_malloc`.

```
sudo apt-get install hardened_malloc
```

## How to Build deb Package ##

Replace `apparmor-profile-torbrowser` with the actual name of this package with `hardened_malloc` and see [instructions](https://www.whonix.org/wiki/Dev/Build_Documentation/apparmor-profile-torbrowser).

## Contact ##

* [Free Forum Support](https://forums.whonix.org)
* [Professional Support](https://www.whonix.org/wiki/Professional_Support)

## Donate ##

`hardened_malloc` requires [donations](https://www.whonix.org/wiki/Donate) to stay alive!
