-----

Usage
-----
You can use this in your terraform template with the following steps.

1. Adding a module resource to your template, e.g. main.tf

    ```
    module "tf-instances" {
        source = "alibaba/ecs-instance/alicloud"

        vswitch_id = "vsw-wqrw3c423"
        group_ids = ["sg-f2c2fwqvs"]
        private_ips = ["172.16.1.10", "172.16.1.20"]

        disk_category = "cloud_ssd"
        disk_name = "my_module_disk"
        disk_size = "50"
        number_of_disks = 2

        instance_name = "my_module_instances"
        host_name = "my-host"
        internet_charge_type = "PayByTraffic"
        number_of_instances = "2"

        key_name = "for-ecs-instance-module"

    }
    ```

2. Setting `access_key` and `secret_key` values through environment variables:

    - ALICLOUD_ACCESS_KEY
    - ALICLOUD_SECRET_KEY


