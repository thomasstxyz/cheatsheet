### export environment variables in github actions workflow

    TF_VAR_EXOSCALE_API_KEY="${{ secrets.TF_VAR_EXOSCALE_API_KEY }}"
    echo "TF_VAR_EXOSCALE_API_KEY=${TF_VAR_EXOSCALE_API_KEY}" >> $GITHUB_ENV

Multiline string

    EOF=$(dd if=/dev/urandom bs=15 count=1 status=none | base64)
    echo "IAC_DEPLOY_KEY<<$EOF" >> $GITHUB_ENV
    echo "${{ secrets.IAC_DEPLOY_KEY }}" >> $GITHUB_ENV
    echo "$EOF" >> $GITHUB_ENV
