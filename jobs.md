# List Background Processes
`$ jobs`

# List Jobs PIDs
`$ jobs -l`

# Run Command and Send to Background
`&`
`$ npm start &`

# Run Command With A Comment
`$ npm start `# Authenticator ``

# Stop Foreground Process
<C-Z>

# Refer To Background Process Number n
%n

# Refer To Background Process By String
%?string

# Restart Background Process
`$ bg`

# Bring Background Process To Foreground
fg
- example: % fg % 1

# Kill A Job Process n
% kill %n

# Create at job
# at runs jobs in parallel
at 4pm

# View Cron tab
crontab -e

# List Cron jobs
crontab -l

# add a Cron job to run at an interval
## m h dayOfMonth month dayOfWeek command

# View at Jobs
atq

# Remove at Jobs
atrm

# Run batch job as long as load below 1.5
# Batch runs jobs sequentially
batch

# View users denied access to at jobs
sudo cat /etc/at.deny

# Manage jobs to run if system is not on, but when system comes online again
## recurrence period, delay in minutes, identifier, command
anacron
