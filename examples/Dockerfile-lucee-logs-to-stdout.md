# Due the fact that Lucee .log files are not created until Tomcat is start
# we need to create this first via "Touch" and symlink theym to STDOUT/STDERR

# Create the log director and TOUCH the .log files
RUN mkdir -p /opt/lucee/web/logs && \
touch /opt/lucee/web/logs/application.log && \
touch /opt/lucee/web/logs/exception.log && \
touch /opt/lucee/web/logs/orm.log && \
touch /opt/lucee/web/logs/mail.log

# Create a link from .log to STDOUT/STDERR
RUN ln -sf /dev/stdout /opt/lucee/web/logs/application.log && \
ln -sf /dev/stdout /opt/lucee/web/logs/exception.log && \
ln -sf /dev/stdout /opt/lucee/web/logs/orm.log && \
ln -sf /dev/stdout /opt/lucee/web/logs/mail.log