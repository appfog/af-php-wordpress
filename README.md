# WordPress compatible with Cloud Foundry

Steps to get the application to run:

1. <code>git clone git://github.com/phpfog/af-sample-wordpress.git</code>
2. <code>cd af-sample-wordpress</code>
3. <code>echo "<?php" > wp-salt.php</code>
4. <code>curl https://api.wordpress.org/secret-key/1.1/salt/ >> wp-salt.php</code>
5. <code>vmc push wordpresscf --url wordpresscf.vcap.me -n</code>
6. <code>vmc create-service mysql --bind wordpresscf</code>
7. Visit http://wordpresscf.vcap.me and enjoy your Wordpress install!

Make sure your Cloud Foundry end-point is compatible with PHP. Right now the only service that can do that is AppFog.com
