# Bash notes
## Scriptdir
SCRIPT_DIR="$( cd "$( dirname "${BASH_SOURCE[0]}" )" && pwd )"

## Colorize in Bash
https://askubuntu.com/questions/135214/pipable-command-to-print-in-color#135225

## Arg parsing v. 1
```for args in "$@"
do
case $args in
    -e=*|--example=*)
    VAR1="${args#*=}"
    shift # past argument=value
    ;;
    -t=*|--test=*)
    TEST="${args#*=}"
    shift # past argument=value
    ;;
    -h|--help)
        help
        exit 1
    ;;
    *)
      # unknown option
      echo -e "Error: unknown command \"$1\" for \"$(basename $0)\" \nRun '$(basename $0) --help' for usage."
      exit 1
    ;;
esac
done
```
