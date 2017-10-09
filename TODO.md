## Lastpass - TypTop integration

1. In `agent.c` file, limne 99:106 need to update this part with password tries fro TypTop. 

```C
    kdf_decryption_key(username, password, iterations, key);

    /* no longer need password contents, zero it */
    secure_clear_str(password);

    verify = config_read_encrypted_string("verify", key);
    if (verify && !strcmp(verify, AGENT_VERIFICATION_STRING))
    break;

```  


2. In `cmd-login.c`, also there is a similar notion of session creation, that can be augmented with TypTop. 


Need to think little bit more, but shouldn't be too hard. 




