result:

    PLAY ***************************************************************************

    TASK [setup] *******************************************************************
    ok: [localhost]

    TASK [dependency : debug] ******************************************************
    ok: [localhost] => {
        "msg": "role1"
    }

    TASK [dependency : set_fact] ***************************************************
    ok: [localhost]

    TASK [dependency : debug] ******************************************************
    ok: [localhost] => {
        "msg": "dependency"
    }

    TASK [dependency : set_fact] ***************************************************
    ok: [localhost]

    PLAY RECAP *********************************************************************
    localhost                  : ok=5    changed=0    unreachable=0    failed=0


expected result:

    PLAY ***************************************************************************

    TASK [setup] *******************************************************************
    ok: [localhost]

    TASK [dependency : debug] ******************************************************
    ok: [localhost] => {
        "msg": "role1"
    }

    TASK [dependency : set_fact] ***************************************************
    ok: [localhost]

    TASK [dependency : debug] ******************************************************
    ok: [localhost] => {
        "msg": "role2"
    }           ^^^^^

    TASK [dependency : set_fact] ***************************************************
    ok: [localhost]

    PLAY RECAP *********************************************************************
    localhost                  : ok=5    changed=0    unreachable=0    failed=0

