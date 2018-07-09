
>>laravel new {project name} #creates laravel project
>>cd {projectname}
>>npm install
>>npm install vuex vue-router --save
     ##>>npm install vuex vue-router validate.js --save
>>Open app with VS @package.json (add what you need)
{
"private": true,
"scripts": {
"live": "php artisan serve --host=127.0.0.1 --port=8000 & npm run hot",
"dev": "npm run development",
"development": "cross-env NODE_ENV=development node_modules/webpack/bin/webpack.js --progress --hide-modules --config=node_modules/laravel-mix/setup/webpack.config.js",
"watch": "npm run development -- --watch",
"watch-poll": "npm run watch -- --watch-poll",
"hot": "cross-env NODE_ENV=development node_modules/webpack-dev-server/bin/webpack-dev-server.js --inline --hot --config=node_modules/laravel-mix/setup/webpack.config.js",
"prod": "npm run production",
"production": "cross-env NODE_ENV=production node_modules/webpack/bin/webpack.js --no-progress --hide-modules --config=node_modules/laravel-mix/setup/webpack.config.js"
},
"devDependencies": {
"babel-preset-env": "^1.7.0",
"babel-preset-stage-2": "^6.24.1",
"cross-env": "^5.1",
"laravel-mix": "^2.1.11"
},
"dependencies": {
"ajv-keywords": "^3.2.0",
"axios": "^0.18",
"bootstrap-vue": "^2.0.0-rc.6",
"fuse.js": "^3.2.0",
"lodash": "^4.17.4",
"popper.js": "^1.12",
"vue": "^2.5.7",
"vue-router": "^3.0.1",
"vuelidate": "^0.6.2",
"vuex": "^3.0.1"
}
}
>>Hookup database & make auth
     > change .env "file"
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE={change}
DB_USERNAME={"your username"}
DB_PASSWORD={"your password"}
     >Open msqlwb make sure its connected
            create schema (same NAME you assigned DB_DATABASE={NAME}
     >In "AppServiceProvider.php" file
          ( on top page add: )
               use Illuminate\Support\Facades\Schema;
          (add class on boot() )
               Schema::defaultStringLength(191);
>>php artisan migrate
>>php artisan make:auth
>>npm run dev
>>npm run live

