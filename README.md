# Ansible Playbook for sorting/rearranging mail per host to hosts per mail

execute with:
```sh
ansible-playbook -i inventory.yml main.yml -vvv
```

Currently the output of the playbook is:

```json
{
    "combined_mail_to_hosts": [
    {
        "test1@example.com": [
            "test1"
        ],
        "test2@example.com": [
            "test1"
        ]
    },
    {
        "test2@example.com": [
            "test2"
        ],
        "test3@example.com": [
            "test2"
        ]
    }
    ]
}
```

But it should look like this:

```json
{
    "combined_mail_to_hosts": 
    {
        "test1@example.com": [
            "test1"
        ],     
        "test2@example.com": [
            "test1",
            "test2"
        ],
        "test3@example.com": [
            "test2"
        ]
    }    
}
```

It want to send a single email to every address with all hosts in it. Not 2 or more mails.