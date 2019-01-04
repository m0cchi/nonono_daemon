# NononoDaemon
Notification Service

## Installation
```ruby
source "https://rubygems.org"

gem "nonono_daemon"
# gem nonono_sender
# gem nonono_reciever

```

### Sample

```Dockerfile
FROM ruby

ENV SLACK_API_TOKEN=xoxp-XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
ENV SLACK_CHANNEL=#XXXXXXXXXXXXXXXXXXXXX
ENV NONONO_HTTP_PORT=4567
ENV NONONO_HTTP_USER=userid
ENV NONONO_HTTP_PASSWORD=password
EXPOSE 4567

RUN cd && mkdir app && cd app \
  && bundle init \
  && echo '' >> Gemfile \
  && echo 'gem "nonono_daemon"' >> Gemfile \
  && echo 'gem "nonono_sender-http"' >> Gemfile \
  && echo 'gem "nonono_reciever-slack"' >> Gemfile \
  && bundle install
CMD cd && cd app && bundle exec nonono
```

## License

The gem is available as open source under the terms of the [MIT License](https://opensource.org/licenses/MIT).
