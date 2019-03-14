Given two sets of structured json data ( see samples) , this playbook will convert json dicts to lists, organize hosts into group:vars by os, then match name/hostname values to their corresponding ip addresses, creating an ansible inventory file.

Please change the vars at the top of the playbook to reflect your directories and whatever changes to file names you want to use:

    jsondata: "{{ lookup('file','sample_topo.json')|from_json }}"
    jsonmetadata: "{{ lookup('file','sample_metadata.json')|from_json }}"
    project_name: "test_project_name"
    project_directory: "/some_project_folder"
    inventory_template_src: "/Users/josesanchez/Qsync/OSI/NetworkCI/json_dict/hosts.j2"
    inventory_template_dest: "/Users/josesanchez/Qsync/OSI/NetworkCI/json_dict/test_host.ini"
    hostvar_template_src:
    hostvar_template_dest:
