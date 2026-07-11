# apiservice
Api service for k8s build

ab -k -c 5 -n 20000 'http://192.168.0.20/' & \
ab -k -c 5 -n 2000 'http://192.168.0.20/status/400' & \
ab -k -c 5 -n 3000 'http://192.168.0.20/status/409' & \
ab -k -c 5 -n 5000 'http://192.168.0.20/status/500' & \
ab -k -c 50 -n 5000 'http://192.168.0.20/status/200?seconds_sleep=1' & \
ab -k -c 50 -n 2000 'http://192.168.0.20/status/200?seconds_sleep=2'