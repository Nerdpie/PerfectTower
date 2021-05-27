# AI Scripts and Utilities for Perfect Tower II
This is my collection of AI scripts. I focus on low-RAM scripts (i.e. 14 actions or less), so that they'll be usable by everyone who has unlocked the AI.

## Auto mining script
This pair of scripts mines across all tabs, at 16x speed (i.e. all squares simultaneously). It takes ~3 seconds to mine 10 layers * 12 tabs at the default 120 FPS. The max actions required is __7__, which should be accessible to everyone.

```
DiggerMaster 1 0 7
DiggerHead 0 0 6

Drag-select both lines to copy everything at once, or triple-click to copy and import an individual script.

DERpZ2dlck1hc3RlcgEAAAAJb3Blbi5taW5lAAAAAAcAAAAOZ2xvYmFsLmludC5zZXQIY29uc3RhbnQECGRyaWxscG9zCGNvbnN0YW50AgAAAAAPZ2VuZXJpYy5leGVjdXRlCGNvbnN0YW50BApEaWdnZXJIZWFkEWdlbmVyaWMud2FpdHVudGlsDmNvbXBhcmlzb24uaW50Dmdsb2JhbC5pbnQuZ2V0CGNvbnN0YW50BAhkcmlsbHBvcwhjb25zdGFudAQCPT0IY29uc3RhbnQCEQAAAA1sb2NhbC5pbnQuc2V0CGNvbnN0YW50BAN0YWIOYXJpdGhtZXRpYy5pbnQNbG9jYWwuaW50LmdldAhjb25zdGFudAQDdGFiCGNvbnN0YW50BAErCGNvbnN0YW50AgEAAAAIbWluZS50YWINbG9jYWwuaW50LmdldAhjb25zdGFudAQDdGFiDW1pbmUubmV3bGF5ZXIMZ2VuZXJpYy5nb3RvC3Rlcm5hcnkuaW50Dm1pbmUuaGFzTGF5ZXJzCGNvbnN0YW50AgYAAAALdGVybmFyeS5pbnQOY29tcGFyaXNvbi5pbnQNbG9jYWwuaW50LmdldAhjb25zdGFudAQDdGFiCGNvbnN0YW50BAE8CGNvbnN0YW50Ag0AAAAIY29uc3RhbnQCBAAAAAhjb25zdGFudAJjAAAA
;CkRpZ2dlckhlYWQAAAAAAAAAAAYAAAAOZ2xvYmFsLmludC5zZXQIY29uc3RhbnQECGRyaWxscG9zDmFyaXRobWV0aWMuaW50Dmdsb2JhbC5pbnQuZ2V0CGNvbnN0YW50BAhkcmlsbHBvcwhjb25zdGFudAQBKwhjb25zdGFudAIBAAAAD2dlbmVyaWMuZXhlY3V0ZQ50ZXJuYXJ5LnN0cmluZw5jb21wYXJpc29uLmludA5nbG9iYWwuaW50LmdldAhjb25zdGFudAQIZHJpbGxwb3MIY29uc3RhbnQEATwIY29uc3RhbnQCEQAAAAhjb25zdGFudAQKRGlnZ2VySGVhZAhjb25zdGFudAQADWxvY2FsLmludC5zZXQIY29uc3RhbnQEA3Bvcw5hcml0aG1ldGljLmludA5nbG9iYWwuaW50LmdldAhjb25zdGFudAQIZHJpbGxwb3MIY29uc3RhbnQEAS0IY29uc3RhbnQCAgAAAAhtaW5lLmRpZw5hcml0aG1ldGljLmludA1sb2NhbC5pbnQuZ2V0CGNvbnN0YW50BANwb3MIY29uc3RhbnQEA21vZAhjb25zdGFudAIEAAAADmFyaXRobWV0aWMuaW50DWxvY2FsLmludC5nZXQIY29uc3RhbnQEA3Bvcwhjb25zdGFudAQBLwhjb25zdGFudAIEAAAADmdlbmVyaWMuZ290b2lmCGNvbnN0YW50AgQAAAASdG93bi53aW5kb3cuaXNvcGVuCGNvbnN0YW50BARtaW5lDGdsb2JhbC51bnNldAhjb25zdGFudAQIZHJpbGxwb3M=

```

## Factory management scripts
The first one is a simple ore crushing/dust up-tiering combo. This works stand-alone, but pairs nicely with other factory automation that expects dust to be available. At __10__ actions, this should also work for everyone. (It can go as low as 7, but by default it includes 3 overrides.) It tries to crush any un-crushed ores, and up-tiers dust while keeping a certain buffer of each type. Edit the first line which sets the variable "dust_safety_buffer" to customize; the default of 200 should be reasonable. You can also override individual tiers by setting "buffer_override_t<num>". It works equally well with or without Chemical Lumps, but if you don't have Lumps it will undershoot the buffer by 4 dust (but it will never consume the last dust, no matter what).

```
D0S.DustManager 1 0 10

D0QwUy5EdXN0TWFuYWdlcgEAAAAMb3Blbi5mYWN0b3J5AAAAAAoAAAAQbG9jYWwuZG91YmxlLnNldAhjb25zdGFudAQSZHVzdF9zYWZldHlfYnVmZmVyCGNvbnN0YW50AwAAAAAAAGlAEGxvY2FsLmRvdWJsZS5zZXQIY29uc3RhbnQEEmJ1ZmZlcl9vdmVycmlkZV90MQhjb25zdGFudAMAAAAAAIjDQBBsb2NhbC5kb3VibGUuc2V0CGNvbnN0YW50BBJidWZmZXJfb3ZlcnJpZGVfdDIIY29uc3RhbnQDAAAAAACIw0AQbG9jYWwuZG91YmxlLnNldAhjb25zdGFudAQSYnVmZmVyX292ZXJyaWRlX3QzCGNvbnN0YW50AwAAAAAAQJ9AD2ZhY3RvcnkucHJvZHVjZQhjb25zdGFudAQDb3JlDmFyaXRobWV0aWMuaW50DWxvY2FsLmludC5nZXQIY29uc3RhbnQECG9yZV90aWVyCGNvbnN0YW50BAErCGNvbnN0YW50AgoAAAATZmFjdG9yeS5pdGVtcy5jb3VudAhjb25zdGFudAQDb3JlDmFyaXRobWV0aWMuaW50DWxvY2FsLmludC5nZXQIY29uc3RhbnQECG9yZV90aWVyCGNvbnN0YW50BAErCGNvbnN0YW50AgoAAAAIY29uc3RhbnQEB2NydXNoZXINbG9jYWwuaW50LnNldAhjb25zdGFudAQIb3JlX3RpZXILdGVybmFyeS5pbnQWZmFjdG9yeS5tYWNoaW5lLmFjdGl2ZQhjb25zdGFudAQHY3J1c2hlcg1sb2NhbC5pbnQuZ2V0CGNvbnN0YW50BAhvcmVfdGllcgt0ZXJuYXJ5LmludA5jb21wYXJpc29uLmludA1sb2NhbC5pbnQuZ2V0CGNvbnN0YW50BAhvcmVfdGllcghjb25zdGFudAQBPghjb25zdGFudAL3////DmFyaXRobWV0aWMuaW50DWxvY2FsLmludC5nZXQIY29uc3RhbnQECG9yZV90aWVyCGNvbnN0YW50BAEtCGNvbnN0YW50AgEAAAAIY29uc3RhbnQCAAAAAA1mYWN0b3J5LmNyYWZ0CGNvbnN0YW50BARsdW1wDmdsb2JhbC5pbnQuZ2V0CGNvbnN0YW50BAlsdW1wX3RpZXIKZG91YmxlLm1pbhFhcml0aG1ldGljLmRvdWJsZRNmYWN0b3J5Lml0ZW1zLmNvdW50CGNvbnN0YW50BARkdXN0DmFyaXRobWV0aWMuaW50Dmdsb2JhbC5pbnQuZ2V0CGNvbnN0YW50BAlsdW1wX3RpZXIIY29uc3RhbnQEASsIY29uc3RhbnQCAQAAAAhjb25zdGFudAQBLQhjb25zdGFudAMAAAAAAADwPxFhcml0aG1ldGljLmRvdWJsZRFhcml0aG1ldGljLmRvdWJsZRNmYWN0b3J5Lml0ZW1zLmNvdW50CGNvbnN0YW50BARkdXN0Dmdsb2JhbC5pbnQuZ2V0CGNvbnN0YW50BAlsdW1wX3RpZXIIY29uc3RhbnQEAS0KZG91YmxlLm1heBFhcml0aG1ldGljLmRvdWJsZQ50ZXJuYXJ5LmRvdWJsZRFjb21wYXJpc29uLmRvdWJsZRBsb2NhbC5kb3VibGUuZ2V0BmNvbmNhdAhjb25zdGFudAQRYnVmZmVyX292ZXJyaWRlX3QDaTJzDmdsb2JhbC5pbnQuZ2V0CGNvbnN0YW50BAlsdW1wX3RpZXIIY29uc3RhbnQEAj09CGNvbnN0YW50AwAAAAAAAAAAEGxvY2FsLmRvdWJsZS5nZXQIY29uc3RhbnQEEmR1c3Rfc2FmZXR5X2J1ZmZlchBsb2NhbC5kb3VibGUuZ2V0BmNvbmNhdAhjb25zdGFudAQRYnVmZmVyX292ZXJyaWRlX3QDaTJzDmdsb2JhbC5pbnQuZ2V0CGNvbnN0YW50BAlsdW1wX3RpZXIIY29uc3RhbnQEAS0IY29uc3RhbnQDAAAAAAAAEEAIY29uc3RhbnQDAAAAAAAA8D8IY29uc3RhbnQEAS8IY29uc3RhbnQDAAAAAAAAIEAPZmFjdG9yeS5wcm9kdWNlCGNvbnN0YW50BARsdW1wDmdsb2JhbC5pbnQuZ2V0CGNvbnN0YW50BAlsdW1wX3RpZXITZmFjdG9yeS5pdGVtcy5jb3VudAhjb25zdGFudAQEbHVtcA5nbG9iYWwuaW50LmdldAhjb25zdGFudAQJbHVtcF90aWVyCGNvbnN0YW50BAVtaXhlcg5nbG9iYWwuaW50LnNldAhjb25zdGFudAQJbHVtcF90aWVyC3Rlcm5hcnkuaW50DmNvbXBhcmlzb24uaW50Dmdsb2JhbC5pbnQuZ2V0CGNvbnN0YW50BAlsdW1wX3RpZXIIY29uc3RhbnQEATwIY29uc3RhbnQCAQAAAAhjb25zdGFudAIBAAAAC3Rlcm5hcnkuaW50D2NvbXBhcmlzb24uYm9vbBZmYWN0b3J5Lm1hY2hpbmUuYWN0aXZlCGNvbnN0YW50BAVtaXhlcghjb25zdGFudAQBfA9jb21wYXJpc29uLmJvb2wSdG93bi53aW5kb3cuaXNvcGVuCGNvbnN0YW50BAdmYWN0b3J5CGNvbnN0YW50BAI9PQhjb25zdGFudAEADmdsb2JhbC5pbnQuZ2V0CGNvbnN0YW50BAlsdW1wX3RpZXILdGVybmFyeS5pbnQOY29tcGFyaXNvbi5pbnQOZ2xvYmFsLmludC5nZXQIY29uc3RhbnQECWx1bXBfdGllcghjb25zdGFudAQBPAhjb25zdGFudAIJAAAADmFyaXRobWV0aWMuaW50Dmdsb2JhbC5pbnQuZ2V0CGNvbnN0YW50BAlsdW1wX3RpZXIIY29uc3RhbnQEASsIY29uc3RhbnQCAQAAAAhjb25zdGFudAIBAAAADmdlbmVyaWMuZ290b2lmCGNvbnN0YW50AgUAAAASdG93bi53aW5kb3cuaXNvcGVuCGNvbnN0YW50BAdmYWN0b3J5

```
